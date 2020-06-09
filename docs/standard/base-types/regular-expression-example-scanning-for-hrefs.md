---
title: 'Esempio di espressione regolare: ricerca di HREF'
description: Vedere un esempio di espressioni regolari in .NET. Nell'esempio viene eseguita la ricerca di una stringa di input e vengono visualizzati tutti i valori degli attributi href e le relative posizioni
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- searching with regular expressions, examples
- parsing text with regular expressions, examples
- regular expressions, examples
- .NET Framework regular expressions, examples
- regular expressions [.NET Framework], examples
- pattern-matching with regular expressions, examples
ms.assetid: fae2c15b-7adf-4b15-b118-58eb3906994f
ms.openlocfilehash: 36273901ac9afb762ac70ee5d6dcd80ff0ede11d
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84583492"
---
# <a name="regular-expression-example-scanning-for-hrefs"></a>Esempio di espressione regolare: ricerca di HREF
Nell'esempio riportato di seguito viene cercata una stringa di input e vengono visualizzati tutti i valori href="…" e le relative posizioni nella stringa.  
  
## <a name="the-regex-object"></a>L'oggetto Regex  
 Poiché il metodo `DumpHRefs` può essere chiamato più volte dal codice utente, viene usato il metodo `static` (`Shared` in Visual Basic) <xref:System.Text.RegularExpressions.Regex.Match%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType>. In questo modo il motore delle espressioni regolari memorizza nella cache l'espressione regolare ed evita il sovraccarico di un'istanza di un nuovo oggetto <xref:System.Text.RegularExpressions.Regex> ogni volta che viene chiamato il metodo. Viene quindi usato un oggetto <xref:System.Text.RegularExpressions.Match> per eseguire un'iterazione in tutte le corrispondenze nella stringa.  
  
 [!code-csharp[RegularExpressions.Examples.HREF#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.HREF/cs/example.cs#1)]
 [!code-vb[RegularExpressions.Examples.HREF#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.HREF/vb/example.vb#1)]  
  
 Nell'esempio seguente viene illustrata una chiamata al metodo `DumpHRefs`.  
  
 [!code-csharp[RegularExpressions.Examples.HREF#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.HREF/cs/example.cs#2)]
 [!code-vb[RegularExpressions.Examples.HREF#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.HREF/vb/example.vb#2)]  
  
 Il criterio di ricerca di espressioni regolari `href\s*=\s*(?:["'](?<1>[^"']*)["']|(?<1>\S+))` è interpretato nel modo illustrato nella tabella seguente.  
  
|Modello|Descrizione|  
|-------------|-----------------|  
|`href`|Corrisponde alla stringa letterale "href". La corrispondenza non fa distinzione tra maiuscole e minuscole.|  
|`\s*`|Trovare la corrispondenza di zero o più spazi vuoti.|  
|`=`|Corrisponde al segno di uguale.|  
|`\s*`|Trovare la corrispondenza di zero o più spazi vuoti.|  
|`(?:\["'\](?<1>\[^"'\]*)["']|(?<1>\S+))`|Senza l'assegnazione del risultato a un gruppo acquisito, corrisponde a uno degli elementi seguenti:<br /> <ul><li><p>Una virgoletta o un apostrofo, seguito da zero o più occorrenze di qualsiasi carattere diverso dai primi, seguito da una virgoletta o un apostrofo. Il gruppo denominato `1` è incluso in questo modello.</p></li><li><p>Uno o più caratteri diversi dallo spazio vuoto. Il gruppo denominato `1` è incluso in questo modello.</p></li></ul>|  
|`(?<1>[^"']*)`|Assegnare zero o più occorrenze di qualsiasi carattere diverso da una virgoletta o un apostrofo al gruppo di acquisizione denominato `1`.|  
|`(?<1>\S+)`|Assegnare uno o più caratteri diversi da spazi vuoti al gruppo di acquisizione denominato `1`.|  
  
## <a name="match-result-class"></a>Classe di risultati di corrispondenza  
 I risultati della ricerca vengono archiviati nella classe <xref:System.Text.RegularExpressions.Match>, che offre l'accesso a tutte le sottostringhe estratte dalla ricerca. Tale classe memorizza anche la stringa cercata e l'espressione regolare usata, pertanto è possibile chiamare il metodo <xref:System.Text.RegularExpressions.Match.NextMatch%2A?displayProperty=nameWithType> per eseguire un'altra ricerca a partire dal punto in cui è terminata quella più recente.  
  
## <a name="explicitly-named-captures"></a>Acquisizioni denominate in modo esplicito  
 Nelle espressioni regolari tradizionali, le parentesi di cattura vengono automaticamente numerate in sequenza. Ciò comporta due problemi. In primo luogo, se un'espressione regolare viene modificata dall'inserimento o rimozione di un set di parentesi, tutto il codice che fa riferimento alle catture numerate deve essere riscritto per riflettere la nuova numerazione. In secondo luogo, poiché diversi set di parentesi spesso vengono usati per specificare due espressioni alternative per una corrispondenza accettabile, potrebbe essere difficile determinare quale delle due espressioni ha effettivamente restituito un risultato.  
  
 Per risolvere questi problemi, la classe <xref:System.Text.RegularExpressions.Regex> supporta la sintassi `(?<name>…)` per l'acquisizione di una corrispondenza in uno slot specificato (che è possibile denominare tramite una stringa o un numero intero, che può essere chiamato più rapidamente). Le corrispondenze alternative per la stessa stringa possono perciò essere tutte indirizzate verso la stessa posizione. In caso di conflitto, l'ultima corrispondenza rilasciata in uno slot è quella corretta. (È tuttavia disponibile un elenco completo di più corrispondenze per un unico slot. Vedere la raccolta <xref:System.Text.RegularExpressions.Group.Captures%2A?displayProperty=nameWithType> per i dettagli.  
  
## <a name="see-also"></a>Vedere anche

- [Espressioni regolari .NET](regular-expressions.md)
