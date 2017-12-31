# Computing-for-Engineers


% Matthew

k=load('board_sample.txt','r');
p=length(k);
x=k(:,1);
y=k(:,2);
w=k(:,3);
h=k(:,4);
a=k(:,5);
for i=1:p
    r=rand();
    g=rand();
    b=rand();
    rectangle('Position',[x(i),y(i),w(i),h(i)],'FaceColor',[r g b],'EdgeColor',[0.05 0.05 0.3],'LineWidth',2)
    hold on
    rectangle('Position',[1 1 5 5],'Curvature',[1],'FaceColor',[0.2 0.6 0.8],'EdgeColor',[0.05 0.05 0.3],'LineWidth',2)
rectangle('Position',[4 4 5 5],'Curvature',[1],'FaceColor',[0.9 0.1 0.1],'EdgeColor',[0.05 0.05 0.3],'LineWidth',2)
rectangle('Position',[6 1 5 5],'Curvature',[1],'FaceColor',[0.1 0.9 0.1],'EdgeColor',[0.05 0.05 0.3],'LineWidth',2)
rectangle('Position',[1 5 5 5],'Curvature',[1],'FaceColor',[0.1 0.1 0.1],'EdgeColor',[0.05 0.05 0.3],'LineWidth',2)
end

text(10,5,char('Start'),'FontName','Verdana')
text(88,90,char('Finish'),'FontName','Verdana')
hold off
