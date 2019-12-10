---
layout: post

title: Paper-reading-neural-hawkes-process
date: 2019-12-10 16:32:24.000000000 +09:00
---

#### About
  
   今天重新梳理之前了解的关于point process的内容，然后总结阅读的论文--The neural hawkes process:A neurally self-modulating multivarite point process(NIPS2017)的内容。
	
#### Motivation

    <1> Main motivation：Capture effects that hawkes process misses;(过去时间对当前事件除了激励作用，还有抑制作用)  
    <2> Second motivation：Cope with missing data;(Real dataet omit some event(illegal drug use or offline purchases)
    which have a strong influence on the future,to learn the distribution, to solve this problem)  
    <3> Final motivation: Reinforce learning,where an agent controls some events;  

#### Problem
    
	Assumes an event of type k occurs in the infinitesimally wide intervak[t, t+dt],with proablity >=0;  
	
#### Model
    <1> SE-MPP(Self-Exciting Multivarite Point Process):hawkes过程，只考虑过去事件对当前事件的激励;  
    <2> D-SE-MPP:(D to decomposable:hawkes process with inhibition):同时考虑过去事件对当前事件的激励和抑制;    
    <3> N-SE-MPP: (neural hawkes process): model with continous-time LSTM;  

#### Main contirbution(In my opinion):
    结合对hawke process的了解，我认为本文的最大贡献在于continous-time LSTM的提出，
    以往的LSTM中，Cell state的变化考虑的是一个interval到另一个interval的变化，
    本文提出的continous-time LSTM考虑了两个interval之间的cell state的变化，也就是之前事件对当前事件影响的衰减性。  

#### Future Work
    Combine with reinforce learning,whice means a continous-reinforce learning,
    decide time to send feedback,whice kind of feedback,(agent)time to response and what respones;  
	
#### Doubts
    <1> 亮点是否就是两个相邻时间间隔内信息的积累;  
	<2> continous-time LSTM 和 traditional LSTM的区别是否就在 time interval内cell state的变化，然后hidden state 根据变化后的cell state 更新;  
	<3> What is sigmoidal tranfer function?  
	<4> N-SE-MPP中，取消过去事件对当前事件独立影响的添加限制？  
	<5> The resulting could be negative, then pass it through a non-linear trasfor function?  
