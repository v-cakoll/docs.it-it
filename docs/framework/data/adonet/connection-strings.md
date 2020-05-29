---
title: Stringhe di connessione
ms.date: 10/10/2018
ms.assetid: 745c5f95-2f02-4674-b378-6d51a7ec2490
ms.openlocfilehash: 3f56a487121757706ef6b4dfd11fcd761657431a
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2020
ms.locfileid: "84202272"
---
# <a name="connection-strings-in-adonet"></a>Stringhe di connessione in ADO.NET

Una stringa di connessione contiene informazioni di inizializzazione che vengono passate come parametro da un provider di dati a un'origine dati. Il provider di dati riceve la stringa di connessione come valore della <xref:System.Data.Common.DbConnection.ConnectionString?displayProperty=nameWithType> Proprietà. Il provider analizza la stringa di connessione e garantisce che la sintassi sia corretta e che le parole chiave siano supportate. Quindi il <xref:System.Data.Common.DbConnection.Open?displayProperty=nameWithType> metodo passa i parametri di connessione analizzati all'origine dati. L'origine dati esegue una convalida ulteriore e stabilisce una connessione.

## <a name="connection-string-syntax"></a>Sintassi delle stringhe di connessione

Una stringa di connessione è un elenco delimitato da punti e virgola di coppie di parametri chiave/valore:

```csharp
keyword1=value; keyword2=value;
```

Le parole chiave non fanno distinzione tra maiuscole e minuscole. I valori, tuttavia, possono fare distinzione tra maiuscole e minuscole, a seconda dell'origine dati. Sia le parole chiave che i valori possono contenere [spazi vuoti](https://en.wikipedia.org/wiki/Whitespace_character#Unicode). Gli spazi vuoti iniziali e finali vengono ignorati nelle parole chiave e nei valori non racchiusi tra virgolette.

Se un valore contiene il punto e virgola, i [caratteri di controllo Unicode](https://en.wikipedia.org/wiki/Unicode_control_characters)o gli spazi vuoti iniziali o finali, è necessario racchiuderlo tra virgolette singole o doppie. Ad esempio:

```csharp
Keyword=" whitespace  ";
Keyword='special;character';
```

Il carattere di inclusione potrebbe non essere presente nel valore che racchiude. Pertanto, un valore contenente virgolette singole può essere racchiuso tra virgolette doppie e viceversa:

```csharp
Keyword='double"quotation;mark';
Keyword="single'quotation;mark";
```

È anche possibile utilizzare un carattere di escape per il carattere di inclusione utilizzandone due:

```csharp
Keyword="double""quotation";
Keyword='single''quotation';
```

Le virgolette stesse, così come il segno di uguale, non richiedono l'escape, quindi sono valide le seguenti stringhe di connessione:

```csharp
Keyword=no "escaping" 'required';
Keyword=a=b=c
```

Poiché ogni valore viene letto fino al punto e virgola successivo o alla fine della stringa, il valore nel secondo esempio è `a=b=c` e il punto e virgola finale è facoltativo.

Tutte le stringhe di connessione condividono la stessa sintassi di base descritta in precedenza. Il set di parole chiave riconosciute dipende tuttavia dal provider e si è evoluto negli anni dalle API precedenti, ad esempio *ODBC*. Il provider di dati *.NET Framework* per *SQL Server* ( `SqlClient` ) supporta molte parole chiave delle API precedenti, ma è in genere più flessibile e accetta sinonimi per molte delle parole chiave comuni della stringa di connessione.

La digitazione degli errori può causare errori. Ad esempio, `Integrated Security=true` è valido, ma `IntegratedSecurity=true` genera un errore.

Le stringhe di connessione costruite manualmente in fase di esecuzione dall'input dell'utente non convalidato sono vulnerabili agli attacchi di stringa Injection e compromettono la sicurezza nell'origine dati. Per risolvere questi problemi, in *ADO.NET* 2,0 sono stati introdotti i [generatori di stringhe di connessione](connection-string-builders.md) per ogni provider di dati *.NET Framework* . Questi generatori di stringhe di connessione espongono parametri come proprietà fortemente tipizzate e rendono possibile la convalida della stringa di connessione prima che venga inviata all'origine dati.

## <a name="in-this-section"></a>Contenuto della sezione

[Generatori di stringhe di connessione](connection-string-builders.md)\
Viene illustrato come usare le classi `ConnectionStringBuilder` per creare stringhe di connessione valide in fase di esecuzione.

[Stringhe di connessione e file di configurazione](connection-strings-and-configuration-files.md)\
Viene illustrato come archiviare e recuperare le stringhe di connessione nei file di configurazione.

[Sintassi delle stringhe di connessione](connection-string-syntax.md)\
Viene descritto come configurare stringhe di connessione specifiche del provider per `SqlClient`, `OracleClient`, `OleDb` e `Odbc`.

[Protezione delle informazioni di connessione](protecting-connection-information.md)\
Vengono illustrate tecniche per proteggere le informazioni usate per la connessione a un'origine dati.

## <a name="see-also"></a>Vedere anche

- [Connessione a un'origine dati](/cpp/data/odbc/connecting-to-a-data-source)
- [Panoramica di ADO.NET](ado-net-overview.md)
