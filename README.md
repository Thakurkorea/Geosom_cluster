https://www.mathworks.com/help/stats/evalclusters.html
# Geosom_optimal clusters
% X=gss.Som.codebook;
oclusters=[];     % optimal clusters
for i =1:200
X=gss.NumData(:,4:end);
E = evalclusters(X,'kmeans','DaviesBouldin','klist',[1:35]);
oclusters=[sclusters;E.OptimalK];
end
xx=mod(oclusters)
hist(oclusters)
xlabel('Optimal clusters')
ylabel('Frequency')
figure
plot(E)
% kmeans(X,xx);
