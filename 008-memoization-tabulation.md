manière de fabriquer de la boite noriede la tabulation plutot que de la memoization

Profiling


import cProfile

ws = make_worksheet()
cProfile.run("profiling.lxml_writer(ws)", sort="tottime")

