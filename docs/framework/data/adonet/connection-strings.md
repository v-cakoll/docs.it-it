---
title: Stringhe di connessione in ADO.NET
ms.date: 10/10/2018
ms.assetid: 745c5f95-2f02-4674-b378-6d51a7ec2490
ms.openlocfilehash: 3b7cb0ab061da8364a9fecc3868ba9aaf7501577
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2019
ms.locfileid: "65881165"
---
# <a name="connection-strings-in-adonet"></a>Stringhe di connessione in ADO.NET

Una stringa di connessione contiene informazioni di inizializzazione che vengono passate come parametro da un provider di dati a un'origine dati. Il provider di dati riceve la stringa di connessione come valore del <xref:System.Data.Common.DbConnection.ConnectionString?displayProperty=nameWithType> proprietà. Il provider consente di analizzare la stringa di connessione e garantisce che la sintassi sia corretta e che le parole chiave sono supportate. Il <xref:System.Data.Common.DbConnection.Open?displayProperty=nameWithType> metodo passa i parametri di connessione analizzato all'origine dati. L'origine dati viene effettuata un'ulteriore convalida e stabilisce una connessione.

## <a name="connection-string-syntax"></a>Sintassi della stringa di connessione

Una stringa di connessione è un elenco delimitato da punto e virgola di coppie chiave/valore parametro:

```
keyword1=value; keyword2=value;
```

Le parole chiave non sono tra maiuscole e minuscole. I valori, tuttavia, potrebbero essere tra maiuscole e minuscole, a seconda dell'origine dati. Entrambe le parole chiave e i valori possono contenere [spazi vuoti](https://en.wikipedia.org/wiki/Whitespace_character#Unicode). Spazi vuoti iniziali e finali viene ignorato nelle parole chiave e senza virgolette i valori.

Se il valore contiene il punto e virgola, [caratteri di controllo Unicode](https://en.wikipedia.org/wiki/Unicode_control_characters), o iniziali o finali lo spazio vuoto, deve essere racchiuso tra virgolette singole o doppie. Ad esempio:

```
Keyword=" whitespace  ";
Keyword='special;character';
```

Il carattere che lo contiene potrebbe non verificarsi all'interno del valore che racchiude. Pertanto, un valore che contiene virgolette singole può essere racchiusi solo tra virgolette doppie e viceversa:

```
Keyword='double"quotation;mark';
Keyword="single'quotation;mark";
```

Le virgolette se stessi, nonché il segno di uguale, non richiede l'escape, in modo che le stringhe di connessione seguenti sono valide:

```
Keyword=no "escaping" 'required';
Keyword=a=b=c
```

Poiché ogni valore viene letto fino alla fine della stringa o il successivo punto e virgola, il valore nell'esempio di quest'ultimo è `a=b=c`, e il punto e virgola finale è facoltativo.

Tutte le stringhe di connessione condividono la stessa sintassi di base descritta in precedenza. Il set di parole chiave riconosciute dipende dal provider, tuttavia e si è evoluto nel corso degli anni dalle precedenti API, ad esempio *ODBC*. Il *.NET Framework* provider di dati per *SQL Server* (`SqlClient`) supporta numerose parole chiave dalle API precedenti, ma è in genere più flessibile e accetta i sinonimi per molti della stringa di connessione comuni parole chiave.

Errori di digitazione può provocare errori. Ad esempio, `Integrated Security=true` valido, ma `IntegratedSecurity=true` provoca un errore.

Le stringhe di connessione costruite manualmente in fase di esecuzione dall'input dell'utente non convalidato sono vulnerabili agli attacchi injection di stringa e compromettano sicurezza nell'origine dati. Per risolvere questi problemi *ADO.NET* 2.0 ha introdotto [generatori di stringhe di connessione](../../../../docs/framework/data/adonet/connection-string-builders.md) per ogni *.NET Framework* provider di dati. I generatori di stringhe di connessione espongono parametri come proprietà fortemente tipizzate e consentono di convalidare la stringa di connessione prima che venga inviata all'origine dati.

## <a name="in-this-section"></a>In questa sezione

[Generatori di stringhe di connessione](../../../../docs/framework/data/adonet/connection-string-builders.md)\
Viene illustrato come usare le classi `ConnectionStringBuilder` per creare stringhe di connessione valide in fase di esecuzione.

[Le stringhe di connessione e file di configurazione](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md)\
Viene illustrato come archiviare e recuperare le stringhe di connessione nei file di configurazione.

[Sintassi della stringa di connessione](../../../../docs/framework/data/adonet/connection-string-syntax.md)\
Viene descritto come configurare stringhe di connessione specifiche del provider per `SqlClient`, `OracleClient`, `OleDb` e `Odbc`.

[Protezione delle informazioni di connessione](../../../../docs/framework/data/adonet/protecting-connection-information.md)\
Vengono illustrate tecniche per proteggere le informazioni usate per la connessione a un'origine dati.

## <a name="see-also"></a>Vedere anche

- [Connessione a un'origine dati](/cpp/data/odbc/connecting-to-a-data-source)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
