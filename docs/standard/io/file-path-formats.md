---
title: Formati dei percorsi di file nei sistemi Windows
ms.date: 06/06/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- I/O, long paths
- long paths
- path formats, Windows
ms.openlocfilehash: 258cf59fb8383fe131f4a0e78dac6189e1d9c91e
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75337666"
---
# <a name="file-path-formats-on-windows-systems"></a>Formati dei percorsi di file nei sistemi Windows

I membri di molti tipi nello spazio dei nomi <xref:System.IO> includono un parametro `path` che consente di specificare un percorso assoluto o relativo di una risorsa del file system. Questo percorso viene quindi passato alle [API del file system Windows](/windows/desktop/fileio/file-systems). Questo argomento descrive i formati per i percorsi di file che è possibile usare nei sistemi Windows.

## <a name="traditional-dos-paths"></a>Percorsi DOS tradizionali

Un percorso DOS standard può essere costituito da tre componenti:

- Un volume o una lettera di unità seguita dal separatore di volume (`:`).
- Un nome di directory. Il [carattere separatore di directory](<xref:System.IO.Path.DirectorySeparatorChar>) separa le sottodirectory all'interno della gerarchia di directory annidata.
- Un nome file facoltativo. Il [carattere separatore di directory](<xref:System.IO.Path.DirectorySeparatorChar>) separa il percorso e il nome del file.

Se sono presenti tutti e tre i componenti, il percorso è assoluto. Se non si specifica alcun volume o lettera di unità e il nome della directory inizia con il [carattere separatore di directory](<xref:System.IO.Path.DirectorySeparatorChar>), il percorso è relativo dalla radice dell'unità corrente. In caso contrario, il percorso è relativo alla directory corrente. La tabella seguente illustra alcuni percorsi possibili di directory e file.

|Percorso  |Descrizione  |
| -- | -- |
| `C:\Documents\Newsletters\Summer2018.pdf` | Percorso file assoluto dalla radice dell'unità C: |
| `\Program Files\Custom Utilities\StringFinder.exe` | Percorso assoluto dalla radice dell'unità corrente. |
| `2018\January.xlsx` | Percorso relativo a un file in una sottodirectory della directory corrente. |
| `..\Publications\TravelBrochure.pdf` | Percorso relativo a un file in una directory che è un peer della directory corrente. |
| `C:\Projects\apilibrary\apilibrary.sln` | Percorso assoluto a un file dalla radice dell'unità C: |
| `C:Projects\apilibrary\apilibrary.sln` | Percorso relativo dalla directory corrente dell'unità C: |

> [!IMPORTANT]
> Si noti la differenza tra gli ultimi due percorsi. Entrambi specificano l'identificatore di volume facoltativo (C: in entrambi i casi), ma il primo inizia con la radice del volume specificato, mentre il secondo no. Di conseguenza, il primo è un percorso assoluto dalla directory radice dell'unità C:, mentre il secondo è un percorso relativo dalla directory corrente dell'unità C:. L'uso del secondo formato quando si intende usare il primo è una fonte comune di bug per i percorsi di file Windows.

È possibile determinare se un percorso di file è completo (ovvero se il percorso è indipendente dalla directory corrente e non cambia quando la directory corrente viene modificata) chiamando il metodo <xref:System.IO.Path.IsPathFullyQualified%2A?displayProperty=nameWthType>. Si noti che tale percorso può includere segmenti di directory relativi (`.` e `..`) ed essere comunque completo se il percorso risolto punta sempre alla stessa posizione.

L'esempio seguente illustra la differenza fra percorsi assoluti e relativi. Si presuppone che la directory D:\FY2018\ esista e che non sia stata impostata alcuna directory corrente per D:\ dal prompt dei comandi prima di eseguire l'esempio.

[!code-csharp[absolute-and-relative-paths](~/samples/snippets/standard/io/file-names/cs/paths.cs)]
[!code-vb[absolute-and-relative-paths](~/samples/snippets/standard/io/file-names/vb/paths.vb)]

## <a name="unc-paths"></a>Percorsi UNC

I percorsi UNC (Universal Naming Convention), che vengono usati per accedere alle risorse di rete, hanno il formato seguente:

- Un nome host o server, preceduto da \\\\. Il nome del server può essere un nome computer NetBIOS o un indirizzo IP/FQDN (sono supportati IPv4 e v6).
- Un nome condivisione, separato dal nome host da \\. Insieme, il server e il nome condivisione costituiscono il volume.
- Un nome di directory. Il [carattere separatore di directory](<xref:System.IO.Path.DirectorySeparatorChar>) separa le sottodirectory all'interno della gerarchia di directory annidata.
- Un nome file facoltativo. Il [carattere separatore di directory](<xref:System.IO.Path.DirectorySeparatorChar>) separa il percorso e il nome del file.

Di seguito sono riportati alcuni esempi di percorsi UNC:

|Percorso  |Descrizione  |
| -- | -- |
| `\\system07\C$\` | Directory radice dell'unità C: in `system07`. |
| `\\Server2\Share\Test\Foo.txt` | File Foo.txt nella directory Test del volume \\\\Server2\\Share.|

I percorsi UNC devono essere sempre completi. Possono includere segmenti di directory relativi (`.` e `..`), ma devono far parte di un percorso completo. È possibile usare i percorsi relativi solo eseguendo il mapping di un percorso UNC a una lettera di unità.

## <a name="dos-device-paths"></a>Percorsi del dispositivo DOS

Il sistema operativo Windows ha un modello a oggetti unificato che punta a tutte le risorse, inclusi i file. Questi percorsi degli oggetti sono accessibili dalla finestra della console e vengono esposti al livello Win32 tramite una cartella speciale di collegamenti simbolici a cui sono mappati i percorsi UNC e DOS legacy. Questa cartella speciale è accessibile tramite la sintassi del percorso del dispositivo DOS, ovvero uno dei due riportati di seguito:

`\\.\C:\Test\Foo.txt`
`\\?\C:\Test\Foo.txt`

Oltre a identificare un'unità con la relativa lettera di unità, è possibile identificare un volume usando l'identificatore univoco globale (GUID) del volume. Assume il formato:

`\\.\Volume{b75e2c83-0000-0000-0000-602f00000000}\Test\Foo.txt`
`\\?\Volume{b75e2c83-0000-0000-0000-602f00000000}\Test\Foo.txt`

> [!NOTE]
> La sintassi del percorso del dispositivo DOS è supportata nelle implementazioni .NET in esecuzione in Windows a partire da .NET Core 1.1 e .NET Framework 4.6.2.

Il percorso del dispositivo DOS è costituito dai componenti seguenti:

- L'identificatore del percorso del dispositivo (`\\.\` o `\\?\`), che identifica il percorso come percorso di un dispositivo DOS.

   > [!NOTE]
   > `\\?\` è supportato in tutte le versioni di .NET Core e in .NET Framework a partire dalla versione 4.6.2.

- Un collegamento simbolico all'oggetto dispositivo "reale" (C: nel caso di un nome di unità o Volume{b75e2c83-0000-0000-0000-602f00000000} nel caso di un GUID del volume).

   Il primo segmento del percorso del dispositivo DOS dopo l'identificatore del percorso del dispositivo identifica il volume o l'unità (ad esempio, `\\?\C:\` e `\\.\BootPartition\`).

   È disponibile un collegamento specifico per i percorsi UNC, chiamato `UNC`. Ad esempio:

  `\\.\UNC\Server\Share\Test\Foo.txt`
  `\\?\UNC\Server\Share\Test\Foo.txt`

    Per i percorsi UNC del dispositivo, la parte server/condivisione costituisce il volume. Ad esempio, in `\\?\server1\e:\utilities\\filecomparer\` la parte server/condivisione è server1\utilities. Ciò risulta particolarmente importante quando si chiama un metodo come <xref:System.IO.Path.GetFullPath(System.String,System.String)?displayProperty=nameWithType> con segmenti di directory relativi; non è mai possibile andare oltre il volume.

I percorsi del dispositivo DOS sono completi per definizione. I segmenti di directory relativi (`.` e `..`) non sono consentiti. Le directory correnti non entrano mai in uso.

## <a name="example-ways-to-refer-to-the-same-file"></a>Esempio: modi per fare riferimento allo stesso file

L'esempio seguente illustra alcuni dei modi in cui è possibile fare riferimento a un file quando si usano le API nello spazio dei nomi <xref:System.IO>. L'esempio crea un'istanza di un oggetto <xref:System.IO.FileInfo> e usa le rispettive proprietà <xref:System.IO.FileInfo.Name> e <xref:System.IO.FileInfo.Length> per visualizzare il nome e la lunghezza del file.

[!code-csharp[referring-to-the-same-file](~/samples/snippets/standard/io/file-names/cs/file-refs.cs)]
[!code-vb[referring-to-the-same-file](~/samples/snippets/standard/io/file-names/vb/file-refs.vb)]

## <a name="path-normalization"></a>Normalizzazione del percorso

Quasi tutti i percorsi passati alle API di Windows sono normalizzati. Durante la normalizzazione, Windows esegue la procedura seguente:

- Identifica il percorso.
- Applica la directory corrente ai percorsi parzialmente completi (relativi).
- Converte in forma canonica i separatori di directory e componenti.
- Valuta i componenti di directory relativi (`.` per la directory corrente e `..` per la directory padre).
- Elimina determinati caratteri.

Questa normalizzazione avviene in modo implicito, ma è possibile eseguirla in modo esplicito chiamando il metodo <xref:System.IO.Path.GetFullPath%2A?displayProperty=nameWithType>, che esegue il wrapping di una chiamata alla [funzione GetFullPathName()](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea). È anche possibile chiamare la [funzione GetFullPathName()](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea) di Windows direttamente tramite P/Invoke.

### <a name="identifying-the-path"></a>Identificazione del percorso

Il primo passaggio nella normalizzazione del percorso consiste nell'identificare il tipo di percorso. I percorsi rientrano in una delle categorie seguenti:

- Sono percorsi del dispositivo, vale a dire iniziano con due separatori e un punto interrogativo o un punto (`\\?` o `\\.`).
- Sono percorsi UNC, vale a dire iniziano con due separatori senza un punto interrogativo o un punto.
- Sono percorsi DOS completi, vale a dire iniziano con una lettera di unità, un separatore di volume e un separatore di componenti (`C:\`).
- Definiscono un dispositivo legacy (`CON`, `LPT1`).
- Sono relativi alla radice dell'unità corrente, vale a dire iniziano con un separatore di componenti singolo (`\`).
- Sono relativi alla directory corrente di un'unità specificata, vale a dire iniziano con una lettera di unità, un separatore di volume e nessun separatore di componenti (`C:`).
- Sono relativi alla directory corrente, vale a dire iniziano con qualsiasi altro elemento (`temp\testfile.txt`).

Il tipo di percorso determina se una directory corrente viene applicata o meno in qualche modo. Definisce inoltre qual è la "radice" del percorso.

### <a name="handling-legacy-devices"></a>Gestione dei dispositivi legacy

Se il percorso è un dispositivo DOS legacy come `CON`, `COM1` o `LPT1`, viene convertito in un percorso del dispositivo anteponendo `\\.\` e viene restituito.

Un percorso che inizia con il nome di un dispositivo legacy viene sempre interpretato come dispositivo legacy dal metodo <xref:System.IO.Path.GetFullPath(System.String)?displayProperty=nameWithType>. Ad esempio, il percorso del dispositivo DOS per `CON.TXT` è `\\.\CON` e il percorso del dispositivo DOS per `COM1.TXT\file1.txt` è `\\.\COM1`.

### <a name="applying-the-current-directory"></a>Applicazione della directory corrente

Se un percorso non è completo, Windows applica la directory corrente. I percorsi UNC e dei dispositivi non hanno la directory corrente applicata e neanche un'unità completa con il separatore C:\\.

Se il percorso inizia con un separatore di componenti singolo, viene applicata l'unità della directory corrente. Ad esempio, se il percorso del file è `\utilities` e la directory corrente è `C:\temp\`, la normalizzazione produce `C:\utilities`.

Se il percorso inizia con una lettera di unità, un separatore di volume e nessun separatore di componenti, viene applicata l'ultima directory corrente impostata dalla shell dei comandi per l'unità specificata. Se l'ultima directory corrente non è stata impostata, viene applicata solo l'unità. Ad esempio, se il percorso del file è `D:sources`, la directory corrente è `C:\Documents\` e l'ultima directory corrente nell'unità D: è stata `D:\sources\`, il risultato è `D:\sources\sources`. Questi percorsi "relativi di unità" sono una fonte comune di errori logici per script e programmi. Presupporre che un percorso che inizia con una lettera e i due punti non sia relativo ovviamente non è corretto.

Se il percorso inizia con un elemento diverso da un separatore, vengono applicate l'unità e la directory correnti. Ad esempio, se il percorso è `filecompare` e la directory corrente è `C:\utilities\`, il risultato è `C:\utilities\filecompare\`.

> [!IMPORTANT]
> I percorsi relativi sono pericolosi nelle applicazioni multithreading (vale a dire, la maggior parte delle applicazioni) perché la directory corrente è un'impostazione specifica per il processo. Qualsiasi thread può modificare la directory corrente in qualsiasi momento. A partire da .NET Core 2.1, è possibile chiamare il metodo <xref:System.IO.Path.GetFullPath(System.String,System.String)?displayProperty=nameWithType> per ottenere un percorso assoluto da un percorso relativo e il percorso base (directory corrente) in base a cui si procede alla risoluzione.

### <a name="canonicalizing-separators"></a>Conversione in forma canonica dei separatori

Tutte le barre (`/`) sono convertite nel separatore di Windows standard, la barra rovesciata (`\`). Se sono presenti, una serie di barre che seguono le prime due vengono compresse in una singola barra.

### <a name="evaluating-relative-components"></a>Valutazione dei componenti relativi

Mentre il percorso viene elaborato, vengono valutati tutti i componenti o i segmenti costituiti da un punto singolo o doppio (`.` o `..`):

- Nel caso di un punto singolo, il segmento corrente viene rimosso, perché fa riferimento alla directory corrente.

- Nel caso di un punto doppio, il segmento corrente e quello padre vengono rimossi, perché il punto doppio fa riferimento alla directory padre.

   Le directory padre vengono rimosse solo se non sono oltre la radice del percorso. La radice del percorso dipende dal tipo di percorso. Si tratta dell'unità (`C:\`) per i percorsi DOS, del server/condivisione per i percorsi UNC (`\\Server\Share`) e del prefisso del percorso del dispositivo per i percorsi del dispositivo (`\\?\` o `\\.\`).

### <a name="trimming-characters"></a>Eliminazione di caratteri

Insieme ai separatori e ai segmenti relativi rimossi in precedenza, durante la normalizzazione vengono rimossi alcuni caratteri aggiuntivi:

- Se un segmento termina con un punto singolo, il punto viene rimosso (un segmento di un punto singolo o doppio è normalizzato nel passaggio precedente; un segmento di tre o più punti non è normalizzato ed è in realtà un nome di file/directory valido).

- Se il percorso non termina con un separatore, tutti gli spazi e i punti finali (U+0020) vengono rimossi. Se l'ultimo segmento è semplicemente un punto singolo o doppio, rientra nella regola dei componenti relativi esposta in precedenza.

   Questa regola indica che è possibile creare un nome di directory con uno spazio finale mediante l'aggiunta di un separatore finale dopo lo spazio.

   > [!IMPORTANT]
   > Non creare **mai** una directory o un nome file con uno spazio finale. Gli spazi finali possono rendere difficile o impossibile l'accesso a una directory e le applicazioni riscontrano in genere un errore quando si tenta di gestire directory o file i cui nomi includono spazi finali.

## <a name="skipping-normalization"></a>Esclusione della normalizzazione

Normalmente, qualsiasi percorso passato a un'API di Windows viene effettivamente passato alla [funzione GetFullPathName](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea) e normalizzato. Un'eccezione degna di nota è quando il percorso di un dispositivo inizia con un punto interrogativo anziché con un punto. A meno che il percorso non inizi esattamente con `\\?\` (si noti l'uso della barra rovesciata canonica), viene normalizzato.

Perché escludere la normalizzazione? Per tre motivi principali:

1. Per ottenere l'accesso a percorsi che non sono in genere disponibili ma sono validi. A un file o una directory denominata `hidden.`, ad esempio, è impossibile accedere in qualsiasi altro modo.

1. Per migliorare le prestazioni escludendo la normalizzazione se è già stata eseguita.

1. Solo in .NET Framework, per ignorare il controllo `MAX_PATH` per la lunghezza del percorso in modo da consentire percorsi contenenti più di 259 caratteri. La maggior parte delle API consente questa operazione, con alcune eccezioni.

> [!NOTE]
> .NET Core gestisce i percorsi lunghi in modo implicito e non esegue un controllo `MAX_PATH`. Il controllo `MAX_PATH` si applica solo a .NET Framework.

L'esclusione della normalizzazione e dei controlli MAX_PATH è l'unica differenza tra le sintassi dei due percorsi di dispositivo; altrimenti sono identici. Prestare attenzione quando si esclude la normalizzazione, perché si rischia di creare percorsi difficili da gestire con le "normali" applicazioni.

I percorsi che iniziano con `\\?\` vengono comunque normalizzati se si passano in modo esplicito alla [funzione GetFullPathName](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea).

È possibile passare i percorsi di più di `MAX_PATH` caratteri a [GetFullPathName](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea) senza `\\?\`. Supporta percorsi di lunghezza arbitraria fino alla dimensione massima delle stringhe che Windows è in grado di gestire.

## <a name="case-and-the-windows-file-system"></a>Maiuscole/minuscole e file system di Windows

Una peculiarità del file system di Windows che può confondere gli utenti e gli sviluppatori non Windows è che i nomi di percorsi e directory non fanno distinzione tra maiuscole e minuscole. In altre parole, i nomi di file e directory riflettono l'uso di maiuscole/minuscole delle stringhe usate quando sono stati creati. Ad esempio, la chiamata al metodo

```csharp
Directory.Create("TeStDiReCtOrY");
```

```vb
Directory.Create("TeStDiReCtOrY")
```

crea una directory denominata TeStDiReCtOrY. Se si rinomina una directory o un file per modificare l'uso di maiuscole/minuscole, il nome del file o della directory riflette le maiuscole/minuscole usate quando è stato rinominato. Ad esempio, il codice seguente rinomina un file denominato test.txt in Test.txt:

[!code-csharp[case-and-renaming](~/samples/snippets/standard/io/file-names/cs/rename.cs)]
[!code-vb[case-and-renaming](~/samples/snippets/standard/io/file-names/vb/rename.vb)]

Tuttavia, nei confronti tra i nomi di file e directory non viene fatta distinzione tra maiuscole e minuscole. Se si cerca un file denominato "test.txt", le API del file system .NET non fanno distinzione tra maiuscole e minuscole nel confronto. Test.txt, TEST.TXT, test.TXT e qualsiasi altra combinazione di lettere maiuscole e minuscole corrisponderanno a "test.txt".
