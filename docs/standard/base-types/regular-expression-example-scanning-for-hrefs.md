---
title: 'Esempio di espressione regolare: ricerca di HREF'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "24"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2bc9db7317c7a73f70a2cb83322b8b3a4c3771b9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="regular-expression-example-scanning-for-hrefs"></a>Esempio di espressione regolare: ricerca di HREF
Nell'esempio riportato di seguito viene cercata una stringa di input e vengono visualizzati tutti i valori href="…" e le relative posizioni nella stringa.  
  
## <a name="the-regex-object"></a>L'oggetto Regex  
 Poiché il `DumpHRefs` metodo può essere chiamato più volte dal codice utente, viene utilizzato il `static` (`Shared` in Visual Basic) <xref:System.Text.RegularExpressions.Regex.Match%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType> metodo. In questo modo il motore delle espressioni regolari memorizzare nella cache l'espressione regolare ed evita l'overhead di un'istanza di un nuovo <xref:System.Text.RegularExpressions.Regex> ogni volta che viene chiamato il metodo di oggetto. Oggetto <xref:System.Text.RegularExpressions.Match> oggetto viene quindi utilizzato per scorrere tutte le corrispondenze nella stringa.  
  
 [!code-csharp[RegularExpressions.Examples.HREF#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.HREF/cs/example.cs#1)]
 [!code-vb[RegularExpressions.Examples.HREF#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.HREF/vb/example.vb#1)]  
  
 Nell'esempio seguente viene illustrata una chiamata al metodo `DumpHRefs`.  
  
 [!code-csharp[RegularExpressions.Examples.HREF#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.HREF/cs/example.cs#2)]
 [!code-vb[RegularExpressions.Examples.HREF#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.HREF/vb/example.vb#2)]  
  
 Il criterio di ricerca di espressioni regolari `href\s*=\s*(?:["'](?<1>[^"']*)["']|(?<1>\S+))` è interpretato nel modo illustrato nella tabella seguente.  
  
|Criterio|Descrizione|  
|-------------|-----------------|  
|`href`|Corrisponde alla stringa letterale "href". La corrispondenza non fa distinzione tra maiuscole e minuscole.|  
|`\s*`|Trovare la corrispondenza di zero o più spazi vuoti.|  
|`=`|Trova la corrispondenza di segno di uguale.|  
|`\s*`|Trovare la corrispondenza di zero o più spazi vuoti.|  
|`(?:["'](?<1>[^"']*)"&#124;(?<1>\S+))`|Senza l'assegnazione del risultato a un gruppo acquisito, corrisponde a uno dei seguenti:<br /><br /> -Una virgoletta o un apostrofo, seguito da zero o più occorrenze di qualsiasi carattere diverso da una virgoletta o un apostrofo, seguito da una virgoletta o un apostrofo. Il gruppo denominato `1` è incluso in questo modello.<br />-Uno o più caratteri di spazio non vuoto. Il gruppo denominato `1` è incluso in questo modello.|  
|`(?<1>[^"']*)`|Assegnare zero o più occorrenze di qualsiasi carattere diverso da una virgoletta o un apostrofo al gruppo di acquisizione denominato `1`.|  
|`"(?<1>\S+)`|Assegnare uno o più caratteri diversi da spazi vuoti al gruppo di acquisizione denominato `1`.|  
  
## <a name="match-result-class"></a>Classe di risultati di corrispondenza  
 I risultati della ricerca vengono archiviati nel <xref:System.Text.RegularExpressions.Match> (classe), che fornisce l'accesso a tutte le sottostringhe estratte dalla ricerca. Tale classe memorizza inoltre la stringa di cui eseguire la ricerca e l'espressione regolare utilizzata, pertanto è possibile chiamare il <xref:System.Text.RegularExpressions.Match.NextMatch%2A?displayProperty=nameWithType> metodo per eseguire un'altra ricerca a partire dal punto in cui il penultimo termina.  
  
## <a name="explicitly-named-captures"></a>Acquisizioni denominate in modo esplicito  
 Nelle espressioni regolari tradizionali, le parentesi di cattura vengono automaticamente numerate in sequenza. Ciò comporta due problemi. In primo luogo, se un'espressione regolare viene modificata dall'inserimento o rimozione di un set di parentesi, tutto il codice che fa riferimento alle catture numerate deve essere riscritto per riflettere la nuova numerazione. In secondo luogo, poiché diversi set di parentesi spesso vengono usati per specificare due espressioni alternative per una corrispondenza accettabile, potrebbe essere difficile determinare quale delle due espressioni ha effettivamente restituito un risultato.  
  
 Per risolvere questi problemi, il <xref:System.Text.RegularExpressions.Regex> classe supporta la sintassi `(?<name>…)` per l'acquisizione di una corrispondenza in uno slot specificato (slot può essere denominato tramite una stringa o un numero intero, che può essere richiamato più rapidamente). Le corrispondenze alternative per la stessa stringa possono perciò essere tutte indirizzate verso la stessa posizione. In caso di conflitto, l'ultima corrispondenza rilasciata in uno slot è quella corretta. (È tuttavia disponibile un elenco completo di più corrispondenze per un unico slot. Vedere il <xref:System.Text.RegularExpressions.Group.Captures%2A?displayProperty=nameWithType> raccolta per i dettagli.)  
  
## <a name="see-also"></a>Vedere anche  
 [Espressioni regolari di .NET](../../../docs/standard/base-types/regular-expressions.md)
