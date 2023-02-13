# Nohup 프로세스 종료하기

```
kill -9 `cat save_pid.txt`
rm save_pid.txt
nohup java -jar /home/ubuntu/jenkins/demo-1-0.0.1-SNAPSHOT.jar > /dev/null 2>&1 &
echo $! > save_pid.txt
```

- `nohup` 실행 시 해당 프로세스를 `save_pid.txt`에 저장될 수 있도록 하고 나중에 `cat`으로 해당 `PID`를 불러오면서 `kill`을 시켜준다.

> 참고 자료: https://stackoverflow.com/questions/17385794/how-to-get-the-process-id-to-kill-a-nohup-process