# Computing-for-Engineers


% %% Make into the inputs of a function
% 
% while game==1
%     numberOfPlayers = input('How many players?\n');
%     modeType = input('Mode 1 or Mode 2?\n');
%     THIRD INPUT HERE?????
%     MAKE A FUNCTION OUTTA THIS
%   if modeType==1
%         for i=1:length(numberOfPlayers)
%         diceRoll = randi([1 6]);
%         moves(i) = moves(i)+diceRoll;
%         end
%   else %modeType = 2
%   end
% end

%% Working version
boardSample = load('board_sample.txt');
fid = fopen('diceRollSample1.txt', 'r');
diceRoll = fscanf(fid,'%s');
diceRoll = strsplit(diceRoll,'0');

p1 = diceRoll{1};
for i = 1:length(p1)
   p{1}(i)=str2num(p1(i));
end

p2 = diceRoll{2};
for i = 1:length(p2)
   p{2}(i)=str2num(p2(i));
end

p3 = diceRoll{3};
for i = 1:length(p3)
   p{3}(i)=str2num(p3(i));
end

p4 = diceRoll{4};
for i = 1:length(p4)
   p{4}(i)=str2num(p4(i));
end

r = [0.9 0.9 1.0 1.0 1.0...
     1.0 0.9 0.9 0.9 0.8 0.7...
     0.7 0.6 0.4 0.5 0.4 0.4...
     0.3 0.2 0.1 0.0 0.0 0.1...
     0.2 0.0 0.2 0.5 0.7 0.8];
 
g = [1.0 0.8 0.6 0.6 0.4...
     0.2 0.1 0.0 0.0 0.0 0.0...
     0.0 0.0 0.1 0.3 0.4 0.5...
     0.6 0.7 0.8 0.9 1.0 0.9...
     0.7 0.6 0.6 0.9 1.0 1.0];
 
b = [0.0 .05 0.0 0.0 0.0...
     0.0 0.1 0.1 0.2 0.3 0.3...
     0.4 0.5 0.6 0.8 0.9 0.8...
     0.8 0.8 0.9 0.7 0.6 0.4...
     0.3 0.1 0.0 0.0 0.0 0.1];

x = boardSample(:,1);
y = boardSample(:,2);
w = boardSample(:,3);
h = boardSample(:,4);
a = boardSample(:,5);

for i = 1:length(a)
        switch a(i)
        case -1 %no action
            str1 = '';
            str2 = '';
        case 0 %start
            str1 = 'START';
            str2 = '';
        case 1
            str1 = 'Go back to';
            str2 = ' start';
            
        case 2
            str1 = 'Jump to end';
            str2 = '';
        case 3
            str1 = 'Jump ahead 2';
            str2 = '';
        case 4
            str1 = 'Go back 2';
            str2 = '';
        case 5
            str1 = 'Roll again';
            str2 = '';
        case 6
            str1 = 'Lose a turn';
            str2 = '';
        case 7
            str1 = 'Jump ahead 3 and';
            str2 = ' roll again';
        case 8
            str1 = 'Go back 3 and';
            str2 = ' lose a turn';
        case 9
            str1 = 'EXPRESS PASS';
            str2 = '';
        case 10
            str1 = 'Send others back 2';
            str2 = '';
        case 11
            str1 = 'If even roll, go back';
            str2 = 'to where you were';
        otherwise %end
            str1 = 'FINISH';
            str2 = '';
        end        
rectangle('Position', [x(i) y(i) w(i) h(i)],...
    'FaceColor', [r(i) g(i) b(i)],...
    'EdgeColor', [0.05 0.05 0.03],...
    'LineWidth', 2);
text(x(i)+1, y(i)+5, char(str1, str2),...
    'FontName', 'Arial', 'FontSize', 8);
end

numberOfPlayers = 3;
space = [1; 1; 1; 1];
r = [0.2 0.9 0.1 0.1];
g = [0.6 0.1 0.9 0.1];
b = [0.8 0.1 0.1 0.1];
for i = 1:numberOfPlayers
    token(i) = rectangle('Position',[x(space(i))+i y(space(i)+i) 5 5],...
               'Curvature',1,'FaceColor',[r(i) g(i) b(i)],...
               'EdgeColor',[r(i) g(i) b(i)],'LineWidth',2);
    pause(1)
end
%up to here is good

while true
for i = 1:numberOfPlayers
    space(i) = space(i) + p{i}(1);
    p{i}(1) = [];
    delete(token(i))
    token(i) = rectangle('Position',[x(space(i))+i y(space(i))+i 5 5],...
               'Curvature',1,'FaceColor',[r(i) g(i) b(i)],...
               'EdgeColor',[r(i) g(i) b(i)],'LineWidth',2);
    disp(token(i))
    pause(1)
    delete(token(i))
    %read action for the space the player is now on
    %perform the action
    %if changed space number, update space number
    %redraw token
    token(i) = rectangle('Position',[x(space(i))+i y(space(i))+i 5 5],...
               'Curvature',1,'FaceColor',[r(i) g(i) b(i)],...
               'EdgeColor',[0.05 0.05 0.3],'LineWidth',.5);
    disp(token(i))
    pause(2)
end
end
    
    
