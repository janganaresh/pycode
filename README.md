127.0.0.1 - - [12/Mar/2025 12:31:30] "GET /customer HTTP/1.1" 200 -
Debugging middleware caught exception in streamed response at a point where response headers were already sent.
Traceback (most recent call last):
  File "C:\Users\LENOVO\AppData\Local\Programs\Python\Python310\lib\site-packages\mysql\connector\pooling.py", line 410, in close
    cnx.reset_session()
AttributeError: 'NoneType' object has no attribute 'reset_session'

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File "C:\Users\LENOVO\AppData\Local\Programs\Python\Python310\lib\site-packages\flask\app.py", line 1536, in __call__
    return self.wsgi_app(environ, start_response)
  File "C:\Users\LENOVO\AppData\Local\Programs\Python\Python310\lib\site-packages\flask\app.py", line 1527, in wsgi_app
    ctx.pop(error)
  File "C:\Users\LENOVO\AppData\Local\Programs\Python\Python310\lib\site-packages\flask\ctx.py", line 426, in pop
    app_ctx.pop(exc)
  File "C:\Users\LENOVO\AppData\Local\Programs\Python\Python310\lib\site-packages\flask\ctx.py", line 262, in pop
    self.app.do_teardown_appcontext(exc)
  File "C:\Users\LENOVO\AppData\Local\Programs\Python\Python310\lib\site-packages\flask\app.py", line 1382, in do_teardown_appcontext
    self.ensure_sync(func)(exc)
  File "C:\Users\LENOVO\Downloads\test\app.py", line 1984, in close_db_connection
    db_connection.close()
  File "C:\Users\LENOVO\AppData\Local\Programs\Python\Python310\lib\site-packages\mysql\connector\pooling.py", line 412, in close
    self._cnx_pool.add_connection(cnx)
  File "C:\Users\LENOVO\AppData\Local\Programs\Python\Python310\lib\site-packages\mysql\connector\pooling.py", line 610, in add_connection
    raise PoolError("Failed adding connection; queue is full")
mysql.connector.errors.PoolError: Failed adding connection; queue is full
127.0.0.1 - - [12/Mar/2025 12:31:39] "POST /submit_customerform HTTP/1.1" 200 -
