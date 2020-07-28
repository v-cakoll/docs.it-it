---
title: Gacutil.exe (strumento Global Assembly Cache)
description: Ottenere informazioni dettagliate su Gacutil.exe, lo strumento Global assembly cache. Questo strumento consente di visualizzare e modificare il Global Assembly Cache e la Download Cache.
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- global assembly cache, viewing contents
- viewing assemblies in global assembly cache
- global assembly cache, manipulating contents
- GAC (global assembly cache), Gacutil.exe
- Gacutil.exe
- GAC (global assembly cache), viewing contents
- installing assemblies into global assembly cache
- removing assemblies from global assembly cache
- list of assemblies in global assembly cache
- cache [.NET Framework], global assembly cache
- GAC (global assembly cache), manipulating contents
- global assembly cache, Gacutil.exe
- Global Assembly Cache tool
ms.assetid: 4c7be9c8-72ae-481f-a01c-1a4716806e99
ms.openlocfilehash: 1fe79a09aa99c9d91d8223e7642408a56da20dfe
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166940"
---
# <a name="gacutilexe-global-assembly-cache-tool"></a>Gacutil.exe (strumento Global Assembly Cache)

Lo strumento Global Assembly Cache consente di visualizzare e modificare il contenuto della Global Assembly Cache e della Download Cache.

Viene installato automaticamente con Visual Studio. Per eseguire lo strumento, usare il Prompt dei comandi per gli sviluppatori per Visual Studio (o il prompt dei comandi di Visual Studio in Windows 7). Per altre informazioni, vedere [Prompt dei comandi](developer-command-prompt-for-vs.md).

Al prompt dei comandi digitare quanto segue:

## <a name="syntax"></a>Sintassi

```console
gacutil [options] [assemblyName | assemblyPath | assemblyListFile]
```

## <a name="parameters"></a>Parametri

|Argomento|Descrizione|
|--------------|-----------------|
|*assemblyName*|Nome di un assembly. È possibile fornire un nome di assembly parzialmente specificato, quale `myAssembly`, o un nome di assembly completo, quale `myAssembly, Version=2.0.0.0, Culture=neutral, PublicKeyToken=0038abc9deabfle5`.|
|*assemblyPath*|Nome di un file contenente il manifesto di un assembly.|
|*assemblyListFile*|Percorso di un file di testo ANSI che elenca gli assembly da installare o disinstallare. Per usare un file di testo per installare assembly, specificare il percorso di ciascun assembly in una riga separata del file. I percorsi relativi vengono interpretati rispetto alla posizione di *assemblyListFile*. Per utilizzare un file di testo per disinstallare assembly, specificare il nome completo di ogni assembly in una riga separata del file. Vedere gli esempi di contenuto di *assemblyListFile* più avanti in questo argomento.|

|Opzione|Descrizione|
|------------|-----------------|
|**/cdl**|Elimina il contenuto della Download Cache.|
|**/f**|Specificare questa opzione con le opzioni **/i** o **/i** per forzare la reinstallazione di un assembly. Se un assembly con lo stesso nome esiste già nella Global Assembly Cache, verrà sovrascritto.|
|**/h**[**ELP**]|Visualizza la sintassi e le opzioni di comando dello strumento.|
|**/i** *assemblyPath*|Installa un assembly nella Global Assembly Cache.|
|**/if**  *assemblyPath*|Installa un assembly nella Global Assembly Cache. Se un assembly con lo stesso nome esiste già nella Global Assembly Cache, verrà sovrascritto.<br /><br /> Specificare questa opzione equivale a specificare contemporaneamente le opzioni **/i** e **/f**.|
|**/il** *assemblyListFile*|Installa uno o più assembly specificati in *assemblyListFile* nella Global Assembly Cache.|
|**/ir**  *assemblyPath*<br /><br /> *Schema*<br /><br /> *id*<br /><br /> *description*|Installa un assembly nella Global Assembly Cache e aggiunge un riferimento per contare l'assembly. Con questa opzione è necessario specificare i parametri *assemblyPath*, *scheme*, *id* e *description*. Per una descrizione dei valori validi che è possibile specificare per questi parametri, vedere l'opzione **/r**.<br /><br /> Specificare questa opzione equivale a specificare contemporaneamente le opzioni **/i** e **/r**.|
|**/l** [*assemblyName*]|Elenca il contenuto della Global Assembly Cache. Se si specifica il parametro *assemblyName*, lo strumento elenca solo gli assembly che corrispondono a quel nome.|
|**/ldl**|Elenca il contenuto della cache dei file scaricati.|
|**/lr** [*assemblyName*]|Elenca tutti gli assembly e i conteggi dei riferimenti corrispondenti. Se si specifica il parametro *assemblyName*, lo strumento elenca solo gli assembly che corrispondono al nome e i relativi conteggi dei riferimenti corrispondenti.|
|**/nologo**|Evita la visualizzazione del messaggio di avvio Microsoft.|
|**/r** [*assemblyName &#124; assemblyPath*]<br /><br /> *Schema*<br /><br /> *id*<br /><br /> *description*|Specifica un riferimento analizzato a uno o più assembly da installare o disinstallare. Specificare questa opzione con le opzioni **/i**, **/il**, **/u** o **/ul**.<br /><br /> Per installare un assembly, specificare i parametri *assemblyPath*, *scheme*, *id* e *description* con questa opzione. Per disinstallare un assembly, specificare i parametri *assemblyName*, *scheme*, *id* e *description*.<br /><br /> Per rimuovere un riferimento a un assembly, è necessario specificare gli stessi parametri *scheme*, *id* e *description* specificati con le opzioni **/i** e **/r** (o **/ir**) al momento dell'installazione dell'assembly. Se si sta disinstallando un assembly, questo viene rimosso anche dalla Global Assembly Cache se si tratta dell'ultimo riferimento da rimuovere e se in Windows Installer non ci sono riferimenti residui all'assembly.<br /><br /> Il parametro *scheme* specifica il tipo di schema di installazione. È possibile specificare uno dei valori seguenti:<br /><br /> -UNINSTALL_KEY: specificare questo valore se il programma di installazione aggiunge l'applicazione a installazione applicazioni in Microsoft Windows. La applicazioni si aggiungono a Installazione applicazioni aggiungendo una chiave del Registro di sistema a HKLM\Software\Microsoft\Windows\CurrentVersion.<br />-FilePath: specificare questo valore se il programma di installazione non aggiunge l'applicazione a installazione applicazioni.<br />-OPAQUE: specificare questo valore se la fornitura di una chiave del registro di sistema o di un percorso di file non si applica allo scenario di installazione. Questo valore consente di specificare informazioni personalizzate per il parametro *id*.<br /><br /> Il valore da specificare per il parametro *id* dipende dal valore specificato per il parametro *scheme*:<br /><br /> -Se si specifica UNINSTALL_KEY per il parametro *Scheme* , specificare il nome del set di applicazioni nella chiave del registro di sistema HKLM\Software\Microsoft\Windows\CurrentVersion.. Se ad esempio la chiave del Registro di sistema è HKLM\Software\Microsoft\Windows\CurrentVersion\MyApp, specificare MyApp per il parametro *id*.<br />- Se si specifica FILEPATH per il parametro *scheme*, specificare il percorso completo del file eseguibile che installa l'assembly come parametro *id*.<br />- Se si specifica OPAQUE per il parametro *scheme*, è possibile specificare qualsiasi porzione di dati come parametro *id*. I dati specificati devono essere racchiusi tra virgolette ("").<br /><br /> Il parametro *description* consente di specificare testo descrittivo sull'applicazione da installare. Queste informazioni vengono visualizzate quando vengono enumerati i riferimenti.|
|**/Silent**|Evita la visualizzazione di tutto l'output.|
|**/u**  *assemblyName*|Disinstalla un assembly dalla cache di assembly globale.|
|**/uf**  *assemblyName*|Forza la disinstallazione di un assembly specificato rimuovendone tutti i riferimenti.<br /><br /> Specificare questa opzione equivale a specificare contemporaneamente le opzioni **/u** e **/f**. **Nota:** non è possibile usare questa opzione per rimuovere un assembly installato con Microsoft Windows Installer. Se si tenta di eseguire questa operazione, verrà visualizzato un messaggio di errore.|
|**/ul** *assemblyListFile*|Disinstalla uno o più assembly specificati in *assemblyListFile* dalla Global Assembly Cache.|
|**/u**[**ngen**] *assemblyName*|Disinstalla un assembly specificato dalla Global Assembly Cache. Se l'assembly specificato dispone di conteggi dei riferimenti esistenti, verranno visualizzati i conteggi dei riferimenti e l'assembly non verrà rimosso dalla Global Assembly Cache. **Nota:** in .NET Framework versione 2.0 l'opzione `/ungen` non è supportata. Usare invece il comando `uninstall` di [Ngen.exe (generatore di immagini native)](ngen-exe-native-image-generator.md). <br /><br /> Se si specifica **/ungen** in .NET Framework versioni 1.0 e 1.1, Gacutil.exe rimuove l'assembly dalla cache delle immagini native. In questa cache vengono archiviate le immagini native degli assembly create usando il [generatore di immagini native (Ngen.exe)](ngen-exe-native-image-generator.md).|
|**/ur**  *assemblyName*<br /><br /> *Schema*<br /><br /> *id*<br /><br /> *description*|Disinstalla un riferimento a un assembly specificato dalla Global Assembly Cache. Per rimuovere un riferimento a un assembly, è necessario specificare gli stessi parametri *Scheme*, *ID*e *Description* specificati con le opzioni **/i** e **/r** (o **/IR)** durante l'installazione dell'assembly. Per una descrizione dei valori validi che è possibile specificare per questi parametri, vedere l'opzione **/r**.<br /><br /> Specificare questa opzione equivale a specificare contemporaneamente le opzioni **/u** e **/r**.|
|**/?**|Visualizza la sintassi e le opzioni di comando dello strumento.|

## <a name="remarks"></a>Osservazioni

> [!NOTE]
> È necessario disporre dei privilegi di amministratore per utilizzare Gacutil.exe.

In particolare, Gacutil.exe consente di installare e rimuovere assembly dalla cache, nonché elencare il contenuto della cache stessa.

Gacutil.exe offre opzioni che supportano un conteggio dei riferimenti simile allo schema di conteggio dei riferimenti supportato da Windows Installer. È possibile utilizzare Gacutil.exe per installare due applicazioni che installano lo stesso assembly in quanto consente di tenere traccia del numero di riferimenti all'assembly. Di conseguenza, l'assembly resta sul computer fino alla completa disinstallazione di entrambe le applicazioni. Se si utilizza Gacutil.exe per l'installazione di prodotti effettivi, utilizzare le opzioni che supportano il conteggio dei riferimenti. Usare le opzioni **/i** e **/r** insieme per installare un assembly e aggiungere un riferimento per il conteggio. Usare le opzioni **/u** e **/r** insieme per rimuovere un conteggio dei riferimenti per un assembly. Se le opzioni **/i** e **/u** vengono usate singolarmente, il conteggio dei riferimenti non sarà supportato. Queste opzioni sono utili durante lo sviluppo dei prodotti ma non per l'installazione di prodotti effettivi.

Usare le opzioni **/il** o **/ul** per installare o disinstallare un elenco di assembly archiviati in un file di testo ANSI. Il contenuto del file di testo deve essere formattato correttamente. Per usare un file di testo per installare assembly, specificare il percorso di ciascun assembly in una riga separata del file. Nell'esempio che segue viene illustrato il contenuto di un file contenente assembly da installare.

```text
myAssembly1.dll
myAssembly2.dll
myAssembly3.dll
```

Per utilizzare un file di testo per disinstallare assembly, specificare il nome completo di ogni assembly in una riga separata del file. Nell'esempio che segue viene illustrato il contenuto di un file contenente assembly da disinstallare.

```text
myAssembly1,Version=1.1.0.0,Culture=en,PublicKeyToken=874e23ab874e23ab
myAssembly2,Version=1.1.0.0,Culture=en,PublicKeyToken=874e23ab874e23ab
myAssembly3,Version=1.1.0.0,Culture=en,PublicKeyToken=874e23ab874e23ab
```

> [!NOTE]
> Se si prova a installare un assembly con un nome di file più lungo rispetto a una lunghezza compresa tra 79 e 91 caratteri (esclusa l'estensione di file), è possibile che venga generato l'errore seguente:
>
> ```output
> Failure adding assembly to the cache:   The file name is too long.
> ```
>
> Ciò avviene perché Gacutil.exe crea internamente un percorso con un numero massimo di caratteri definito da MAX_PATH e costituito dagli elementi seguenti:
>
> - Radice della Global Assembly Cache: 34 caratteri (ad esempio, `C:\Windows\Microsoft.NET\assembly\`)
> - Architettura: 7 o 9 caratteri (ad esempio, `GAC_32\`, `GAC_64\`, `GAC_MSIL`)
> - AssemblyName: fino a 91 caratteri, a seconda delle dimensioni degli altri elementi (ad esempio, `System.Xml.Linq\`)
> - AssemblyInfo: da 31 a 48 caratteri o un numero maggiore, costituito da:
>   - Framework: 5 caratteri (ad esempio, `v4.0_`)
>   - AssemblyVersion: da 8 a 24 caratteri (ad esempio, `9.0.1000.0_`)
>   - AssemblyLanguage. da 1 a 8 caratteri (ad esempio, `de_`, `sr-Cyrl_`)
>   - PublicKey: 17 caratteri (ad esempio, `31bf3856ad364e35\`)
> - DllFileName: fino a 91 + 4 caratteri (ad esempio, `<AssemblyName>.dll`)

## <a name="examples"></a>Esempi

Il comando che segue installa l'assembly `mydll.dll` nella Global Assembly Cache.

```console
gacutil /i mydll.dll
```

Il comando che segue rimuove l'assembly `hello` dalla Global Assembly Cache purché non esista alcun conteggio dei riferimenti per l'assembly.

```console
gacutil /u hello
```

Si noti che il comando precedente può causare la rimozione di più assembly dalla cache dell'assembly in quanto il nome dell'assembly non è completo. Se ad esempio nella cache sono installate sia la versione 1.0.0.0 che la versione 3.2.2.1 di `hello`, il comando `gacutil /u hello` rimuoverà entrambi gli assembly.

L'esempio che segue illustra come evitare che vengano rimossi più assembly. Questo comando rimuove solo l'assembly `hello` corrispondente al numero di versione, alle impostazioni cultura e alla chiave pubblica specificati in modo completo.

```console
gacutil /u hello, Version=1.0.0.1, Culture="de",PublicKeyToken=45e343aae32233ca
```

Il comando che segue installa gli assembly specificati nel file `assemblyList.txt` nella Global Assembly Cache.

```console
gacutil /il assemblyList.txt
```

Il comando che segue rimuove gli assembly specificati nel file `assemblyList.txt` dalla Global Assembly Cache.

```console
gacutil /ul assemblyList.txt
```

Il comando che segue installa `myDll.dll` nella Global Assembly Cache e aggiunge un riferimento per il conteggio. L'assembly `myDll.dll` viene utilizzato dall'applicazione `MyApp`. Il parametro `UNINSTALL_KEY MyApp` specifica la chiave del Registro di sistema che aggiunge `MyApp` a Installazione applicazioni in Windows. Il parametro relativo alla descrizione è specificato come `My Application Description`.

```console
gacutil /i /r myDll.dll UNINSTALL_KEY MyApp "My Application Description"
```

Il comando che segue installa `myDll.dll` nella Global Assembly Cache e aggiunge un riferimento per il conteggio. Il parametro relativo allo schema, `FILEPATH`, e quello relativo all'id, `c:\applications\myApp\myApp.exe`, specificano il percorso dell'applicazione che installa `myDll.dll.` Il parametro relativo alla descrizione è specificato come `MyApp`.

```console
gacutil /i /r myDll.dll FILEPATH c:\applications\myApp\myApp.exe MyApp
```

Il comando che segue installa `myDll.dll` nella Global Assembly Cache e aggiunge un riferimento per il conteggio. Il parametro relativo allo schema, `OPAQUE`, consente di personalizzare i parametri relativi all'id e alla descrizione.

```console
gacutil /i /r mydll.dll OPAQUE "Insert custom application details here" "Insert Custom description information here"
```

Il comando che segue rimuove il riferimento a `myDll.dll` dall'applicazione `myApp`. Se si tratta dell'ultimo riferimento all'assembly, verrà rimosso anche l'assembly dalla Global Assembly Cache.

```console
gacutil /u /r myDll.dll FILEPATH c:\applications\myApp\myApp.exe MyApp
```

Il comando che segue elenca il contenuto della Global Assembly Cache.

```console
gacutil /l
```

## <a name="see-also"></a>Vedere anche

- [Strumenti](index.md)
- [Global Assembly Cache](../app-domains/gac.md)
- [Regasm.exe (strumento di registrazione degli assembly)](regasm-exe-assembly-registration-tool.md)
- [Prompt dei comandi](developer-command-prompt-for-vs.md)
