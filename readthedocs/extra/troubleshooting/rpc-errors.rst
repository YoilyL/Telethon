==========
RPC Errors
==========

RPC stands for Remote Procedure Call, and when Telethon raises an
``RPCError``, it’s most likely because you have invoked some of the API
methods incorrectly (wrong parameters, wrong permissions, or even
something went wrong on Telegram’s server). The most common are:

-  ``FloodError`` (420), the same request was repeated many times. Must
   wait ``.seconds``.
-  ``SessionPasswordNeededError``, if you have setup two-steps
   verification on Telegram.
-  ``CdnFileTamperedError``, if the media you were trying to download
   from a CDN has been altered.
-  ``ChatAdminRequiredError``, you don’t have permissions to perform
   said operation on a chat or channel. Try avoiding filters, i.e. when
   searching messages.

The generic classes for different error codes are: \* ``InvalidDCError``
(303), the request must be repeated on another DC. \*
``BadRequestError`` (400), the request contained errors. \*
``UnauthorizedError`` (401), the user is not authorized yet. \*
``ForbiddenError`` (403), privacy violation error. \* ``NotFoundError``
(404), make sure you’re invoking ``Request``\ ’s!

If the error is not recognised, it will only be an ``RPCError``.