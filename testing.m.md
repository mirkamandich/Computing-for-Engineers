# Computing-for-Engineers


fid=fopen('diceRollSample1.txt','r');
diceRoll=fscanf(fid,'%s');
diceRoll=strsplit(diceRoll,'0');
diceRollP1=diceRoll{1};
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
