# provide-parameters-to-main-
给main函数提供参数，比如一个数组
C++ Primer P196-6.2.5-main:处理命令行选项
    int main(int argc, char *argv[])
    or
    int main(int argc, char **argv)
    需要注意到的一点
    argv的第一个元素指向程序的名字或者一个空字符串，即argv[0]一般是没用的
    想要读取数据或者文件
    要从argv[1]开始
    【具体说明见p197】
    
    还有一个比较好的例子
    在p285-自动构造和析构
    考虑一个程序，它的main函数接受一个要处理的文件列表。可能需要以下循环
    //对每个传递给程序的文件执行循环操作
        int main(int argc, char **argv)
        for(auto p = argv+1; p != argv + argc; ++p)
            ifstream input(argv[1])
                if(input){
                    process(input);
                }
                else{
                    cerr<<" "<<endl;
                }
    具体解释看书
