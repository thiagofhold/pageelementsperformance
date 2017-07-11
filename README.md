# pageelementsperformance
Displays the performance of page elements in a table on the console.

Copy this code and paste at Console, when the page is fully load.

	var pagePerformance = [];
	for (var i = 0; i < performance.getEntries().length; i++) {
		var nomePerformance = performance.getEntries()[i]["name"];
		var tipoPerformance = performance.getEntries()[i]["initiatorType"];
		var tamanhoPerformance = performance.getEntries()[i]["transferSize"];
		var tempoPerformance = performance.getEntries()[i]["duration"];

		var construindo = {
		"página":document.URL,
	    "nome":nomePerformance,
	    "tipo":tipoPerformance,
	    "tamanho (em kb)":Number(tamanhoPerformance),
	    "duracao (em milissegundos)":Number(tempoPerformance.toFixed(2))
	}
	pagePerformance.push(construindo);
}
console.table(pagePerformance)
