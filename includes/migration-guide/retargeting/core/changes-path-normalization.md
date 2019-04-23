---
ms.openlocfilehash: d57cd5a9d41a7d2d93f03216d534f14831bcefe0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234932"
---
### <a name="changes-in-path-normalization"></a>Modifica nella normalizzazione del percorso

|   |   |
|---|---|
|Dettagli|A partire dalle app destinate a .NET Framework 4.6.2, il modo in cui il runtime normalizza i percorsi è cambiato. La normalizzazione di un percorso implica la modifica della stringa che identifica un percorso o un file in modo che sia conforme a un percorso valido nel sistema operativo di destinazione. In genere, la normalizzazione implica:<ul><li>La conversione in forma canonica dei separatori di directory e dei componenti.</li><li>L'applicazione della directory corrente in un percorso relativo.</li><li>La valutazione della directory relativa (.) o della directory padre (..) in un percorso.</li><li>La rimozione di caratteri specificati.</li></ul>Le modifiche seguenti per la normalizzazione del percorso sono abilitate per impostazione predefinita a partire dalle app destinate a .NET Framework 4.6.2:<ul><li>Il runtime viene rinviato alla funzione [GetFullPathName](https://docs.microsoft.com/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea) del sistema operativo per normalizzare i percorsi.</li><li>La normalizzazione non consiste più nel rimuovere la fine dei segmenti di directory (ad esempio uno spazio alla fine di un nome di directory).</li><li>Supporto per la sintassi del percorso dispositivo in attendibilità totale, tra cui `\\.\` e, per le API del file I/O in mscorlib.dll, `\\?\`.</li><li>Il runtime non convalida i percorsi di sintassi del dispositivo.</li><li>È supportato l'uso della sintassi del dispositivo per accedere ai flussi di dati alternativi.</li></ul>Queste modifiche migliorano le prestazioni, consentendo al contempo ai metodi di accedere a percorsi in precedenza inaccessibili. Le applicazioni destinate a .NET Framework 4.6.1 e versioni precedenti ma in esecuzione in .NET Framework 4.6.2 o versioni successive non sono interessate da questa modifica.|
|Suggerimento|Le app destinate a .NET Framework 4.6.2 o versioni successive possono rifiutare esplicitamente questa modifica e usare la normalizzazione legacy aggiungendo il codice seguente alla sezione <code>&lt;runtime&gt;</code> del file di configurazione dell'applicazione:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.IO.UseLegacyPathHandling=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>Le app destinate a .NET Framework 4.6.1 o versioni precedenti ma in esecuzione su .NET Framework 4.6.2 o versioni successive possono abilitare le modifiche alla normalizzazione del percorso aggiungendo la riga seguente alla sezione <code>&lt;runtime&gt;</code> del file di configurazione dell'applicazione:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.IO.UseLegacyPathHandling=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Ambito|Secondario|
|Versione|4.6.2|
|Tipo|Ridestinazione|
