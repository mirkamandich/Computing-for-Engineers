# Computing-for-Engineers


clf

hMarker = plot(3,4,'*','markersize',22)

axis([0 100 0 100])

get(hMarker)

pause(2)

set(hMarker,'xdata',33)

set(hMarker,'ydata',44)

%delete(hMarker)   %would delete the player's token

 

hText = text(12,23,'@','fontsize',22,'color','r')

get(hText)

pause(2)

set(hText,'Position',[56,24])

%  delete(hText)   would delete the player's token 

 

hSquare = patch([10 20 20 10 10],[10 10 20 20 10],'g')

get(hSquare)

pause(2)

set(hSquare,'xdata',[20 30 30 20 20])

set(hSquare,'ydata',[20 20 30 30 20])

%  delete(hSquare)   would delete the player's token

mysquare=patch([10 20 20 10 10],[10 10 20 20 10],'g')

get(mysquare)
pause(2)
set(mysquare,'xdata',[10,10,10,10])
set(mysquare,'ydata',[40,40,10,10])
