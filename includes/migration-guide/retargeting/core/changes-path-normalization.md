---
ms.openlocfilehash: d3d336b9626437d8fb597de421005763afd5f021
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/11/2019
ms.locfileid: "67859298"
---
### <a name="changes-in-path-normalization"></a>Modifica nella normalizzazione del percorso

|   |   |
|---|---|
|Dettagli|A partire dalle app destinate a .NET Framework 4.6.2, il modo in cui il runtime normalizza i percorsi è cambiato. La normalizzazione di un percorso implica la modifica della stringa che identifica un percorso o un file in modo che sia conforme a un percorso valido nel sistema operativo di destinazione. In genere, la normalizzazione implica:<ul><li>La conversione in forma canonica dei separatori di directory e dei componenti.</li><li>L'applicazione della directory corrente in un percorso relativo.</li><li>La valutazione della directory relativa (.) o della directory padre (..) in un percorso.</li><li>La rimozione di caratteri specificati.</li></ul>Le modifiche seguenti per la normalizzazione del percorso sono abilitate per impostazione predefinita a partire dalle app destinate a .NET Framework 4.6.2:<ul><li>Il runtime viene rinviato alla funzione [GetFullPathName](https://docs.microsoft.com/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamew) del sistema operativo per normalizzare i percorsi.</li><li>La normalizzazione non consiste più nel rimuovere la fine dei segmenti di directory (ad esempio uno spazio alla fine di un nome di directory).</li><li>Supporto della sintassi del percorso del dispositivo con attendibilità totale, incluso <code>\\.\</code> and, for file I/O APIs in mscorlib.dll, <code>\\?\</code>.</li><li>The runtime does not validate device syntax paths.</li><li>The use of device syntax to access alternate data streams is supported.</li></ul>These changes improve performance while allowing methods to access previously inaccessible paths. Apps that target the .NET Framework 4.6.1 and earlier versions but are running under the .NET Framework 4.6.2 or later are unaffected by this change.|
|Suggerimento|Le app destinate a .NET Framework 4.6.2 o versioni successive possono rifiutare esplicitamente questa modifica e usare la normalizzazione legacy aggiungendo il codice seguente alla sezione <code>&lt;runtime&gt;</code> del file di configurazione dell'applicazione:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.IO.UseLegacyPathHandling=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>Le app destinate a .NET Framework 4.6.1 o versioni precedenti ma in esecuzione su .NET Framework 4.6.2 o versioni successive possono abilitare le modifiche alla normalizzazione del percorso aggiungendo la riga seguente alla sezione <code>&lt;runtime&gt;</code> del file di configurazione dell'applicazione:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.IO.UseLegacyPathHandling=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Ambito|Secondario|
|Versione|4.6.2|
|Tipo|Ridestinazione|

