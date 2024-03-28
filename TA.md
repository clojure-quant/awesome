# technical analysis

https://zorro-project.com/manual/en/ta.htm

https://quantocracy.com/ https://www.quantconnect.com/market/alpha/e219bc8c86278eb3d2d0d8ab6/v1.1

; multiple strategies 
https://github.com/systematicinvestor/SIT/blob/master/R/bt.test.r

https://github.com/joshuaulrich/quantmod





Code
Issues
18
Pull requests
Breadcrumbsquanta
/README-links.md
Latest commit
awb99
awb99
1 hour ago
History
 :b [1 2 3 4 3 3]}
ds/->dataset (ds/column-map :c (fn[a b] (cond (> a 3) 1 (< b 3) -1 :else 0)) [:a :b]))

Or see https://clojurians.zulipchat.com/#narrow/stream/236259-tech.2Eml.2Edataset.2Edev/topic/stupid.20column.20calc/near/244088467 for an alternative

jsa5:33 PM For your specific case, column-map seems like the exact fit. Another option is the more general add-column. Using the tablecloth dplyr / data.table like "wrapper" for TMD, this would look like:

(-> {:a [2 3 4 5 1 1] :b [1 2 3 4 3 3]} tc/dataset (tc/add-column :c #(let [a (:a %) b (:b %)] (mapv (fn[a b] (cond (> a 3) 1 (< b 3) -1 :else 0)) a b)))) => _unnamed [6 3]:

### quantmod
https://github.com/joshuaulrich/quantmod

$ xts : chr [1:27] "apply.daily" "apply.monthly" "apply.quarterly" "apply.weekly" ...
$ quantmod : chr [1:25] "allReturns" "annualReturn" "ClCl" "dailyReturn" ...
$ TTR : chr [1:63] "adjRatios" "ADX" "ALMA" "aroon" ...
$ PerformanceAnalytics: chr [1:7] "Return.annualized" "Return.annualized.excess" "Return.clean" "Return.cumulative" ...
