##中间件
django的中间件类似于java中的面向切面编程，它可以介入django的请求和响应处理过程，修改输入和输出。
每个中间件组件是一个独立的Python类，可以定义下面方法中的一个或多个
* _init _：无需任何参数，服务器响应第一个请求的时候调用一次，用于确定是否启用当前中间件
* process_request(request)：执行视图之前被调用，在每个请求上调用，返回None或HttpResponse对象
* process_view(request, view_func, view_args, view_kwargs)：调用视图之前被调用，在每个请求上调用，返回None或HttpResponse对象
* process_template_response(request, response)：在视图刚好执行完毕之后被调用，在每个请求上调用，返回实现了render方法的响应对象
* process_response(request, response)：所有响应返回浏览器之前被调用，在每个请求上调用，返回HttpResponse对象
* process_exception(request,response,exception)：当视图抛出异常时调用，在每个请求上调用，返回一个HttpResponse对象
使用中间件可以干扰整个处理过程，使得每次请求都会执行中间件的方法。需要激活：即在django的配置文件中的MIDDLEWARE_CLASSESS的元组中。