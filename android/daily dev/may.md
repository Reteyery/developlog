1、handler泄露问题

    常规写法（会提示内存泄露问题）：
    private Handler mHandler = new Handler() {  
        @Override  
        public void handleMessage(Message msg) {  
            super.handleMessage(msg);  
        }  
    };  

    建议：
    private Handler mHandler = new Handler(new Handler.Callback() {  
        @Override  
        public boolean handleMessage(Message msg) {  
            // TODO Auto-generated method stub  
            return false;  
        }  
    }) ;