# Semiconductor-simulation-in-Matlib-first-level
no comment



--------------------------------------------------------------------------------


Matlab simulation.
clear all
%simulation 
stage=100;
LotNum=25*19;
LotMatSum(LotNum,4)=0;
countii(LotNum,4)=0;
for SAT=1:4
    for x=1:LotNum
        LotP=0;
        R=rand(1,100);
        counti=0;
        for i=1 : stage                  
            if(R(i)<=0.09)
            R(i)=0;
            counti=counti+1;
            else
            end
            LotP=LotP+R(i);       
        end
        LotMatSum(x,SAT)=LotP;
        countii(x,SAT)=counti;
    end    
end
LotSum(LotNum,1)=0;
FaiSum(LotNum,1)=0;
for x=1:LotNum
    for SAT=1:4
        LotSum(x)=LotSum(x)+LotMatSum(x,SAT);
        FaiSum(x)=FaiSum(x)+countii(x,SAT);
    end
     LotSum(x)= LotSum(x)/4;
    if( LotSum(x)<0.32 || FaiSum(x)>40)
       LotSum(x)=0;
    else
    end
end
disp(LotSum);% end of simulation

