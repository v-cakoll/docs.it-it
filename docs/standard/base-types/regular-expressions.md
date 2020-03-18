---
title: Espressioni regolari di .NET Framework
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pattern-matching with regular expressions, about pattern-matching
- substrings
- searching with regular expressions, about regular expressions
- pattern-matching with regular expressions
- searching with regular expressions
- parsing text with regular expressions
- regular expressions [.NET Framework], about regular expressions
- regular expressions [.NET Framework]
- .NET Framework regular expressions, about
- characters [.NET Framework], regular expressions
- parsing text with regular expressions, overview
- .NET Framework regular expressions
- strings [.NET Framework], regular expressions
ms.assetid: 521b3f6d-f869-42e1-93e5-158c54a6895d
ms.openlocfilehash: ac034ff37b0b39f41d6f58381286706f9a9ac602
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73121709"
---
# <a name="net-regular-expressions"></a>Espressioni regolari .NET
Le espressioni regolari ("regular expression") garantiscono un metodo efficace e flessibile per elaborare del testo. L'ampia notazione per la formulazione dei criteri di ricerca fornita dalle espressioni regolari consente di analizzare rapidamente grandi quantità di testo per trovare combinazioni di caratteri specifiche, per convalidare il testo verificandone la corrispondenza con un modello predefinito, ad esempio un indirizzo di posta elettronica, per estrarre, modificare, sostituire o eliminare sottostringhe di testo e per aggiungere le stringhe estratte a una raccolta per generare un rapporto. Per numerose applicazioni che gestiscono stringhe o che analizzano grandi blocchi di testo, le espressioni regolari rappresentano uno strumento indispensabile.  
  
## <a name="how-regular-expressions-work"></a>Funzionamento delle espressioni regolari  
 Il motore di elaborazione di testo tramite espressioni regolari è rappresentato dall'oggetto <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType> in .NET. L'elaborazione di testo tramite espressioni regolari richiede che al motore delle espressioni regolari vengano fornite almeno le due informazioni seguenti:  
  
- Criterio di espressione regolare da identificare nel testo.  
  
     In .NET i criteri di espressione regolare vengono definiti a un linguaggio o una sintassi speciale, compatibile con le espressioni regolari Perl 5, che offre funzionalità aggiuntive come la corrispondenza da destra verso sinistra. Per altre informazioni, vedere [Linguaggio di espressioni regolari - Riferimento rapido](regular-expression-language-quick-reference.md).  
  
- Testo da analizzare per il criterio di espressione regolare.  
  
 I metodi della classe <xref:System.Text.RegularExpressions.Regex> consentono di eseguire le operazioni seguenti:  
  
- Determinare se il criterio di espressione regolare è presente nel testo di input chiamando il metodo <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=nameWithType>. Per un esempio di uso del metodo <xref:System.Text.RegularExpressions.Regex.IsMatch%2A> per la convalida del testo, vedere [Procedura: Verificare che le stringhe siano in formato di posta elettronica valido](how-to-verify-that-strings-are-in-valid-email-format.md).  
  
- Recuperare una o tutte le occorrenze del testo che corrispondono al criterio di espressione regolare chiamando il metodo <xref:System.Text.RegularExpressions.Regex.Match%2A?displayProperty=nameWithType> o <xref:System.Text.RegularExpressions.Regex.Matches%2A?displayProperty=nameWithType>. Il primo metodo restituisce un oggetto <xref:System.Text.RegularExpressions.Match?displayProperty=nameWithType> che fornisce informazioni sul testo corrispondente. secondo metodo restituisce un oggetto <xref:System.Text.RegularExpressions.MatchCollection> che contiene un oggetto <xref:System.Text.RegularExpressions.Match?displayProperty=nameWithType> per ogni corrispondenza trovata nel testo analizzato.  
  
- Sostituire il testo che corrisponde al criterio di espressione regolare chiamando il metodo <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType>. Per esempi di uso del metodo <xref:System.Text.RegularExpressions.Regex.Replace%2A> per modificare i formati di data e rimuovere i caratteri non validi da una stringa, vedere [Procedura: Rimuovere caratteri non validi da una stringa](how-to-strip-invalid-characters-from-a-string.md) e [Esempio: Modifica dei formati di data](regular-expression-example-changing-date-formats.md).  
  
 Per una panoramica del modello a oggetti delle espressioni regolari, vedere [Modello a oggetti delle espressioni regolari](the-regular-expression-object-model.md).  
  
 Per altre informazioni sul linguaggio delle espressioni regolari, vedere [Linguaggio di espressioni regolari - Riferimento rapido](regular-expression-language-quick-reference.md) o scaricare e stampare una delle brochure seguenti:  
  
 [Riferimento rapido in formato Word (DOCX)](https://download.microsoft.com/download/D/2/4/D240EBF6-A9BA-4E4F-A63F-AEB6DA0B921C/Regular%20expressions%20quick%20reference.docx)  
 [Riferimento rapido in formato PDF (PDF)](https://download.microsoft.com/download/D/2/4/D240EBF6-A9BA-4E4F-A63F-AEB6DA0B921C/Regular%20expressions%20quick%20reference.pdf)  
  
## <a name="regular-expression-examples"></a>Esempi di espressioni regolari  
 La classe <xref:System.String> include numerosi metodi di ricerca e sostituzione di stringhe che è possibile usare quando si vogliono individuare stringhe letterali in una stringa più grande. Le espressioni regolari sono utili per lo più quando si vuole individuare una di diverse sottostringhe in una stringa più grande o quando si vogliono identificare dei modelli in una stringa, come illustrato negli esempi seguenti.  
  
### <a name="example-1-replacing-substrings"></a>Esempio 1: sostituzione di sottostringhe  
 Si presupponga che una lista di distribuzione contenga nomi che talvolta includono un titolo (Mr., Mrs., Miss o Ms.) oltre al nome e al cognome. Se non si vogliono includere i titoli quando si generano etichette per le buste dall'elenco, è possibile usare un'espressione regolare per rimuovere i titoli, come illustrato nell'esempio seguente.  
  
 [!code-csharp[Conceptual.Regex#2](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex/cs/example1.cs#2)]
 [!code-vb[Conceptual.Regex#2](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex/vb/example1.vb#2)]  
  
 Il criterio di espressione regolare `(Mr\.? |Mrs\.? |Miss |Ms\.? )` trova una corrispondenza di tutte le occorrenze di "Mr", "Mr.", "Mrs", "Mrs.", "Miss", "Ms" o "Ms.". La chiamata al metodo <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType> sostituisce la stringa corrispondente con <xref:System.String.Empty?displayProperty=nameWithType>, ovvero la rimuove dalla stringa originale.  
  
### <a name="example-2-identifying-duplicated-words"></a>Esempio 2: identificazione di parole duplicate  
 La duplicazione accidentale delle parole è un errore comune commesso dagli autori. È possibile usare un'espressione regolare per identificare le parole duplicate, come illustrato nell'esempio seguente.  
  
 [!code-csharp[Conceptual.Regex#3](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex/cs/example2.cs#3)]
 [!code-vb[Conceptual.Regex#3](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex/vb/example2.vb#3)]  
  
 Il criterio di espressione regolare `\b(\w+?)\s\1\b` può essere interpretato nel modo seguente:  
  
|||  
|-|-|  
|`\b`|Inizia dal confine di una parola.|  
|(\w+?)|Corrisponde a uno o più caratteri alfanumerici, ma il minor numero di caratteri possibile. I caratteri insieme formano un gruppo a cui è possibile fare riferimento come `\1`.|  
|`\s`|Trova la corrispondenza con uno spazio vuoto.|  
|`\1`|Trova la corrispondenza della sottostringa equivalente al gruppo denominato `\1`.|  
|`\b`|Trova la corrispondenza di un confine di parola.|  
  
 Il metodo <xref:System.Text.RegularExpressions.Regex.Matches%2A?displayProperty=nameWithType> viene chiamato con le opzioni relative alle espressioni regolari impostate su <xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase?displayProperty=nameWithType>. Per l'operazione di corrispondenza non viene quindi fatta distinzione tra maiuscole e minuscole e nell'esempio la sottostringa "This this" viene identificata come duplicato.  
  
 Si noti che la stringa di input include la sottostringa "this? This". Dato che tuttavia tra le due parole è presente un segno di punteggiatura, le parole non vengono identificate come duplicati.  
  
### <a name="example-3-dynamically-building-a-culture-sensitive-regular-expression"></a>Esempio 3: compilazione dinamica di un'espressione regolare dipendente dalle impostazioni cultura  
 L'esempio seguente illustra le potenzialità delle espressioni regolari combinate alla flessibilità offerta dalle funzionalità di globalizzazione di .NET. Viene usato l'oggetto <xref:System.Globalization.NumberFormatInfo> per determinare il formato dei valori di valuta nelle impostazioni cultura correnti del sistema. Queste informazioni vengono quindi usate per costruire in modo dinamico un'espressione regolare per l'estrazione dei valori di valuta dal testo. Per ogni corrispondenza, viene estratto il sottogruppo che contiene solo la stringa numerica, viene convertito in un valore <xref:System.Decimal> e viene calcolato un totale parziale.  
  
 [!code-csharp[Conceptual.Regex#1](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex/cs/example.cs#1)]
 [!code-vb[Conceptual.Regex#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex/vb/example.vb#1)]  
  
 In un computer le cui impostazioni cultura correnti sono Inglese - Stati Uniti (en-US), l'esempio compila l'espressione regolare `\$\s*[-+]?([0-9]{0,3}(,[0-9]{3})*(\.[0-9]+)?)` dinamicamente. Questo criterio di espressione regolare può essere interpretato nel modo seguente:  
  
|||  
|-|-|  
|`\$`|Cerca una singola occorrenza del simbolo del dollaro (`$`) nella stringa di input. La stringa del criterio di espressione regolare include una barra rovesciata per indicare che il simbolo di dollaro deve essere interpretato letteralmente e non come un ancoraggio dell'espressione regolare. (Il `$` simbolo da solo indicherebbe che il motore delle espressioni regolari deve tentare di iniziare la corrispondenza alla fine di una stringa.) Per garantire che il simbolo di valuta delle impostazioni cultura correnti non <xref:System.Text.RegularExpressions.Regex.Escape%2A?displayProperty=nameWithType> venga interpretato erroneamente come simbolo di espressione regolare, nell'esempio viene chiamato il metodo per eseguire l'escape del carattere.|  
|`\s*`|Cerca zero o più occorrenze di uno spazio vuoto.|  
|`[-+]?`|Cerca zero o una occorrenza di un segno positivo o negativo.|  
|`([0-9]{0,3}(,[0-9]{3})*(\.[0-9]+)?)`|Le parentesi esterne che delimitano questa espressione la definiscono come gruppo di acquisizione o come sottoespressione. Se viene trovata una corrispondenza, è possibile recuperare informazioni relative a questa parte della stringa corrispondente dal secondo oggetto <xref:System.Text.RegularExpressions.Group> nell'oggetto <xref:System.Text.RegularExpressions.GroupCollection> restituito dalla proprietà <xref:System.Text.RegularExpressions.Match.Groups%2A?displayProperty=nameWithType>. Il primo elemento della raccolta rappresenta la corrispondenza completa.|  
|`[0-9]{0,3}`|Cerca da zero a tre occorrenze delle cifre decimali comprese tra 0 e 9.|  
|`(,[0-9]{3})*`|Cerca zero o più occorrenze di un separatore di gruppi seguito da tre cifre decimali.|  
|`\.`|Cerca una singola occorrenza del separatore decimale.|  
|`[0-9]+`|Cerca una o più cifre decimali.|  
|`(\.[0-9]+)?`|Cerca zero o una occorrenza del separatore decimale seguito da almeno una cifra decimale.|  
  
 Se ognuno di questi modelli secondari viene trovato nella stringa di input, la corrispondenza ha esito positivo e un oggetto <xref:System.Text.RegularExpressions.Match> contenente informazioni sulla corrispondenza viene aggiunto all'oggetto <xref:System.Text.RegularExpressions.MatchCollection>.  
  
## <a name="related-topics"></a>Argomenti correlati  
  
|Titolo|Descrizione|  
|-----------|-----------------|  
|[Linguaggio delle espressioni regolari - Guida di riferimento rapidoRegular Expression Language - Quick Reference](regular-expression-language-quick-reference.md)|Fornisce informazioni sul set di caratteri, di operatori e di costrutti che è possibile usare per definire le espressioni regolari.|  
|[Modello a oggetti delle espressioni regolariThe Regular Expression Object Model](the-regular-expression-object-model.md)|Fornisce esempi di codice e informazioni che illustrano l'uso delle classi di espressioni regolari.|  
|[Dettagli sul comportamento delle espressioni regolari](details-of-regular-expression-behavior.md)|Offre informazioni sulle funzionalità e il funzionamento delle espressioni regolari di .NET.|  
|[Esempi di espressioni regolari](regular-expression-examples.md)|Fornisce esempi di codice che illustrano gli usi tipici delle espressioni regolari.|  
  
## <a name="reference"></a>Informazioni di riferimento  
 <xref:System.Text.RegularExpressions?displayProperty=nameWithType>  
 <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType>  
 [Espressioni regolari - Guida di riferimento rapido (download in formato Word)](https://download.microsoft.com/download/D/2/4/D240EBF6-A9BA-4E4F-A63F-AEB6DA0B921C/Regular%20expressions%20quick%20reference.docx)  
 [Espressioni regolari - Guida di riferimento rapido (download in formato PDF)](https://download.microsoft.com/download/D/2/4/D240EBF6-A9BA-4E4F-A63F-AEB6DA0B921C/Regular%20expressions%20quick%20reference.pdf)
