************************************
프로세스 CPU 사용량 확인하기
************************************


장비의 CPU 사용량 확인
========================

linux의 주요 CPU 모니터링 명령어들

* vmstat
* pidstat
* sar
* top

vmstat로 CPU 사용량 확인 (리눅스에서 실행시 확인, 윈도우에서 실행할 경우 스킵할 것 !)
===========================================================================

1. 터미널 화면을 띄운다
2. 다음과 같이 vmstat 명령어를 실행하여 결과를 확인해 본다

.. code-block:: console

    $ vmstat 5
    procs -----------memory---------- ---swap-- -----io---- --system-- -----cpu-----
     r  b   swpd   free   buff  cache   si   so    bi    bo   in   cs us sy id wa st
     0  0 689820 859516 231196 7398616    0    0     0     0    0    0  0  0 100  0  0
     0  0 689820 855364 231196 7398628    0    0     0    18 3384 4577  0  0 100  0  0
     0  0 689820 855380 231196 7398636    0    0     0    35 3303 4652  0  0 100  0  0

(여기서 우측의 5개 열에 있는 0,0,100,0,0 에 주목해야 한다)

3. CPU 관련 데이터만 따로 보면

.. code-block:: console

    $ vmstat 5
    -----cpu-----
    us sy id wa st
    0  0 100  0  0
    0  0 100  0  0
    0  0 100  0  0

User CPU와 System CPU 값이 모두 0으로 매우 낮은지를 확인한다. (실습 CPU 의 상황에 따라서 이 값은 충분히 다를 수 있다)




