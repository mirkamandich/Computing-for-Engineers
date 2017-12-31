# Computing-for-Engineers


function []=moving(player1Rolls)
k=load('board_sample.txt','r');
p=length(k);
x=k(:,1);
y=k(:,2);
w=k(:,3);
h=k(:,4);
for i=1:p
    r=rand();
    g=rand();
    b=rand();
    rectangle('Position',[x(i),y(i),w(i),h(i)],'FaceColor',[r g b],'EdgeColor',[0.05 0.05 0.3],'LineWidth',2)
    hold on
end


fid=fopen('diceRollSample1.txt','r');
diceRoll=fscanf(fid,'%s');
diceRoll=strsplit(diceRoll,'0');

for z=1:length(diceRoll) 
p{z}=diceRoll{z};
    
end

 for i=1:length(diceRollP1)
     player1Rolls(i)=str2num(diceRollP1(i));
 end
 diceRollP2=diceRoll{2};
 for i=1:length(diceRollP2)
     player2Rolls(i)=str2num(diceRollP2(i));
 end
 diceRollP3=diceRoll{3};
 for i=1:length(diceRollP3)
     player3Rolls(i)=str2num(diceRollP3(i));
 end
 diceRollP4=diceRoll{4};
 for i=1:length(diceRollP4)
     player4Rolls(i)=str2num(diceRollP4(i));
 end
x1=1;
y1=1;
x2=4;
y2=4;
x3=6;
y3=1;
x4=1;
y4=5;
    
for i=1:length(player1Rolls)
    Player1=rectangle('Position',[x1 y1 5 5],'Curvature',[1],'FaceColor',[0.2 0.6 0.8],'EdgeColor',[0.05 0.05 0.3],'LineWidth',2)
    x1=x(i+player1Rolls(i));
    y1=y(i+player1Rolls(i));
    pause(1)
delete(Player1)
end
for i=1:length(player2Rolls)
    Player2=rectangle('Position',[x2 y2 5 5],'Curvature',[1],'FaceColor',[0.2 0.6 0.8],'EdgeColor',[0.05 0.05 0.3],'LineWidth',2)
    x2=4+x(i+player2Rolls(i));
    y2=4+y(i+player2Rolls(i));
    
pause(1)
delete(Player2)
end
for i=1:length(player3Rolls)
    Player3=rectangle('Position',[x3 y3 5 5],'Curvature',[1],'FaceColor',[0.2 0.6 0.8],'EdgeColor',[0.05 0.05 0.3],'LineWidth',2)
    x3=6+x(i+player3Rolls(i));
    y3=1+y(i+player3Rolls(i));
    
pause(1)
delete(Player3)
end
for i=1:length(player4Rolls)
    Player4=rectangle('Position',[x4 y4 5 5],'Curvature',[1],'FaceColor',[0.2 0.6 0.8],'EdgeColor',[0.05 0.05 0.3],'LineWidth',2)
    x4=1+x(i+player4Rolls(i));
    y4=5+y(i+player4Rolls(i));
    
pause(1)
delete(Player4)
end





end
