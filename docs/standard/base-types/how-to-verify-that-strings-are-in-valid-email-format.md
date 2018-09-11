---
title: 'Procedura: Verificare che le stringhe siano in formato di posta elettronica valido'
ms.date: 08/10/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- regular expressions, examples
- user input, examples
- Regex.IsMatch method
- regular expressions [.NET Framework], examples
- examples [Visual Basic], strings
- IsValidEmail
- validation, email strings
- input, checking
- strings [.NET Framework], examples [Visual Basic]
- email [.NET Framework], validating
- IsMatch method
ms.assetid: 7536af08-4e86-4953-98a1-a8298623df92
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1fe0ead93d1ff2b7867a52d80cf812e2850ea7b3
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/09/2018
ms.locfileid: "44186539"
---
# <a name="how-to-verify-that-strings-are-in-valid-email-format"></a>Procedura: Verificare che le stringhe siano in formato di posta elettronica valido
L'esempio seguente usa un'espressione regolare per verificare la validità del formato di posta elettronica di una stringa.  

## <a name="example"></a>Esempio  
 Nell'esempio viene definito un metodo `IsValidEmail` che restituisce `true` se nella stringa è presente un indirizzo di posta elettronica valido e `false` in caso contrario, ma non esegue alcuna altra azione.  
  
 Per verificare che l'indirizzo di posta elettronica sia valido, il metodo `IsValidEmail` chiama il metodo <xref:System.Text.RegularExpressions.Regex.Replace%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.MatchEvaluator%29?displayProperty=nameWithType> con il criterio di espressione regolare `(@)(.+)$` per separare il nome di dominio dall'indirizzo di posta elettronica. Il terzo parametro è un delegato <xref:System.Text.RegularExpressions.MatchEvaluator> che rappresenta il metodo che elabora e sostituisce il testo corrispondente. Il criterio di espressione regolare viene interpretato nel modo seguente.  
  
|Modello|Descrizione|  
|-------------|-----------------|  
|`(@)`|Trova la corrispondenza con il carattere @. Equivale al primo gruppo di acquisizione.|  
|`(.+)`|Trova la corrispondenza con una o più occorrenze di qualsiasi carattere. Equivale al secondo gruppo di acquisizione.|  
|`$`|Terminare la corrispondenza alla fine della stringa.|  
  
 Il nome di dominio con il carattere @ viene passato al metodo `DomainMapper` che usa la classe <xref:System.Globalization.IdnMapping> per convertire i caratteri Unicode che si trovano all'esterno dell'intervallo di caratteri US-ASCII a Punycode. Il metodo imposta inoltre il flag `invalid` su `True` se il metodo <xref:System.Globalization.IdnMapping.GetAscii%2A?displayProperty=nameWithType> rileva caratteri non validi nel nome di dominio. Il metodo restituisce il nome di dominio Punycode preceduto dal simbolo @ al metodo `IsValidEmail` .  
  
 Il metodo `IsValidEmail` chiama quindi il metodo <xref:System.Text.RegularExpressions.Regex.IsMatch%28System.String%2CSystem.String%29?displayProperty=nameWithType> per verificare che l'indirizzo sia conforme a un criterio di espressione regolare.  
  
 Si noti che il metodo `IsValidEmail` non esegue l'autenticazione per convalidare l'indirizzo di posta elettronica e si limita a stabilire se il formato è valido per un indirizzo di posta elettronica. Inoltre, il metodo `IsValidEmail` non verifica che il nome di dominio di primo livello sia un nome di dominio valido elencato nella pagina del [Database delle aree radice sul sito IANA](https://www.iana.org/domains/root/db), cosa che richiederebbe un'operazione di ricerca. L'espressione regolare verifica invece solo che il nome di dominio di primo livello sia costituito da un numero di caratteri ASCII compreso tra due e 24. Il nome deve iniziare e finire con caratteri alfanumerici e i caratteri rimanenti possono essere alfanumerici o un trattino (-).  
  
 [!code-csharp[RegularExpressions.Examples.Email#7](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.Email/cs/example4.cs#7)]
 [!code-vb[RegularExpressions.Examples.Email#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.Email/vb/example4.vb#7)]  
  
 In questo esempio il modello di espressione regolare ``^(?(")(".+?(?<!\\)"@)|(([0-9a-z]((\.(?!\.))|[-!#\$%&'\*\+/=\?\^`{}|~\w])*)(?<=[0-9a-z])@))(?([)([(\d{1,3}.){3}\d{1,3}])|(([0-9a-z][-0-9a-z]*[0-9a-z]*.)+[a-z0-9][-a-z0-9]{0,22}[a-z0-9]))$`` viene interpretato come illustrato nella tabella seguente. Si noti che l'espressione regolare viene compilata usando il flag <xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase?displayProperty=nameWithType>.  
  
|Modello|Descrizione|  
|-------------|-----------------|  
|`^`|Iniziare la ricerca della corrispondenza all'inizio della stringa.|  
|`(?(")`|Determinare se il primo carattere corrisponde a una virgoletta. `(?(")` è l'inizio di un costrutto di alternanza.|  
|`(?("")("".+?(?<!\\)""@)`|Se il primo carattere è una virgoletta, cercare la corrispondenza con una virgoletta iniziale seguita da almeno un'occorrenza di qualsiasi carattere, seguita da una virgoletta finale. La virgoletta finale non deve essere preceduta da un carattere di barra rovesciata (\\). `(?<!` è l'inizio dell'asserzione lookbehind negativa di larghezza zero. La stringa dovrebbe terminare con il simbolo @.|  
|<code>&#124;(([0-9a-z]</code>|Se il primo carattere non è una virgoletta, cercare la corrispondenza di qualsiasi carattere alfabetico da a a z o da A a Z (nel confronto è applicata la distinzione tra maiuscole e minuscole) oppure di qualsiasi carattere numerico da 0 a 9.|  
|`(\.(?!\.))`|Se il carattere successivo è un punto, cercare la corrispondenza del punto. Se non è un punto, eseguire il look ahead del carattere successivo e continuare la ricerca della corrispondenza. `(?!\.)` è un'asserzione lookahead negativa di larghezza zero che impedisce la comparsa di due punti consecutivi nella parte locale di un indirizzo di posta elettronica.|  
|<code>&#124;[-!#\$%&'\*\+/=\?\^\`{}\&#124;~\w]</code>|Se il carattere successivo non è un punto, cercare la corrispondenza con qualsiasi carattere alfanumerico o con uno dei caratteri seguenti: -!#$%'*+=?^\`{}&#124;~.|  
|<code>((\.(?!\.))&#124;[-!#\$%'\*\+/=\?\^\`{}\&#124;~\w])*</code>|Cercare la corrispondenza del modello di alternanza (un punto seguito da un carattere diverso dal punto o da uno dei numerosi caratteri) zero o più volte.|  
|`@`|Trova la corrispondenza con il carattere @.|  
|`(?<=[0-9a-z])`|Continuare la ricerca della corrispondenza se il carattere che precede il carattere @ è compreso tra A e Z, tra a e z oppure tra 0 e 9. Il costrutto `(?<=[0-9a-z])` definisce un'asserzione lookbehind positiva di larghezza zero.|  
|`(?(\[)`|Controllare se il carattere che segue @ è una parentesi di apertura.|  
|`(\[(\d{1,3}\.){3}\d{1,3}\])`|Se è una parentesi di apertura, cercare la corrispondenza della parentesi di apertura seguita da un indirizzo IP (quattro set da una a tre cifre, con ogni set separato da un punto) e una parentesi di chiusura.|  
|<code>&#124;(([0-9a-z][-0-9a-z]*[0-9a-z]*\.)+</code>|Se il carattere che segue @ non è una parentesi di apertura, cercare la corrispondenza con un carattere alfanumerico con un valore compreso tra A e Z, a e z oppure 0 e 9, seguito da zero o più occorrenze di un trattino, seguite da zero o un carattere alfanumerico con un valore compreso tra A e Z, a e z oppure 0 e 9, seguito da un punto. Questo modello può essere ripetuto una o più volte e deve essere seguito dal nome di dominio di primo livello.|  
|`[a-z0-9][\-a-z0-9]{0,22}[a-z0-9]))`|Il nome di dominio di primo livello deve iniziare e finire con un carattere alfanumerico (a-z, A-Z e 0-9). Può anche includere da zero a 22 caratteri ASCII, che possono essere caratteri alfanumerici o trattini.|  
|`$`|Terminare la corrispondenza alla fine della stringa.|  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 I metodi `IsValidEmail` e `DomainMapper` possono essere inclusi in una libreria di metodi di utilità di espressioni regolari oppure possono essere inclusi come metodi di istanza o statici privati nella classe dell'applicazione.  
  
 Per includerli in una libreria di espressioni regolari, copiare e incollare il codice in un progetto libreria di classi Visual Studio oppure copiare e incollare il codice in un file di testo e compilarlo dalla riga di comando con un comando simile al seguente (supponendo che il nome del file del codice sorgente sia RegexUtilities.cs o RegexUtilities.vb:  
  
```csharp  
csc /t:library RegexUtilities.cs  
```  
  
```vb  
vbc /t:library RegexUtilities.vb  
```  
  
 È anche possibile usare il metodo <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A?displayProperty=nameWithType> per includere questa espressione regolare in una libreria di espressioni regolari.  
  
 Se vengono usati in una libreria di espressioni regolari, è possibile chiamarli usando il codice seguente:  
  
 [!code-csharp[RegularExpressions.Examples.Email#8](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.Email/cs/example4.cs#8)]
 [!code-vb[RegularExpressions.Examples.Email#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.Email/vb/example4.vb#8)]  
  
 Supponendo di aver creato una libreria di classi denominata RegexUtilities.dll che include l'espressione regolare di convalida tramite posta elettronica, è possibile compilare questo esempio in uno dei modi seguenti:  
  
-   In Visual Studio, creando un'applicazione console e aggiungendo al progetto un riferimento a RegexUtilities.dll.  
  
-   Dalla riga di comando, copiando e incollando il codice sorgente in un file di testo e compilandolo con un comando simile al seguente (supponendo che il nome del file del codice sorgente sia Example.cs o Example.vb:  
  
    ```csharp  
    csc Example.cs /r:RegexUtilities.dll  
    ```  
  
    ```vb  
    vbc Example.vb /r:RegexUtilities.dll  
    ```  
  
## <a name="see-also"></a>Vedere anche

- [Espressioni regolari di .NET Framework](../../../docs/standard/base-types/regular-expressions.md)
