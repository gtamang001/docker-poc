FROM alpine:latest
# create dir 
RUN mkdir /usr/app
# Create a user group 'usergroup' as system group
RUN addgroup -S usergroup

# Create a user 'appuser' under 'usergroup'
RUN adduser -S -D -h /usr/app appuser usergroup

# Chown all the files to the app user.
RUN chown -R appuser:usergroup /usr/app

WORKDIR /usr/app
# Switch to 'appuser'
USER appuser

CMD bash
