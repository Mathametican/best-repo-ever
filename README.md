# best-repo-ever 
List<AggregateResult> result=[SELECT Industry , COUNT(Id) Total
                             From Account GROUP BY Industry];
for(AggregateResult ar:result){
    System.debug('Industry  :'+ar.get('Industry'));
    System.debug('Total Accounts :'+ar.get('Total'));
}
List<AggregateResult> result=[SELECT Industry , COUNT(Id) Total
                             From Account GROUP BY Industry];
for(AggregateResult ar:result){
    System.debug('Industry  :'+ar.get('Industry'));
    System.debug('Total Accounts :'+ar.get('Total'));
}