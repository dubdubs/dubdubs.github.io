用busb命令在命令行中开启一个交互式窗口可以方便我们使用交互式的 shell 会话，与计算节点上的 shell 进程进行交互。
输入bsub + gpu资源指定命令 + -Is /bin/bash，-Is /bin/bash 的意思是直接与计算节点进行交互

## bsub command

- bsub test 提交作业

- bsub -J my_job test 指定作业名称
 
- bsub -q short test 指定队列

- bsub -n 4 test 申请 CPU 核心

- bsub -R "rusage[mem=8G]" test 申请内存

- bsub -R "select[gpu]" -R "rusage[ngpus_excl_p=1]" test 申请 GPU

- bsub -W 02:00 test 设置运行时间

- bsub -o output.log -e error.log test 输出日志

- bsub -I test 交互式运行	

- bsub -w "done(job1_id)" test 依赖任务

- bjobs 查看作业状态

- bkill <jobID> 杀掉某个作业

- bhist 查看作业历史

- bpeek <jobID> 查看作业实时输出

- bqueues 查看所有可用队列
