---
title: Creare i file di risorse per le app .NET
description: Creare file di risorse per le app .NET. Consente di compilare file di testo con risorse di tipo stringa, file XML o binari a livello di codice o file XML con dati di tipo stringa, immagine o oggetto.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- resource files, .resources files
- .resources files
- application resources, creating files
- resource files, creating
ms.assetid: 6c5ad891-66a0-4e7a-adcf-f41863ba6d8d
ms.openlocfilehash: 4730a14e499c75176d7ba7c8378626070d5211e9
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86865177"
---
# <a name="create-resource-files-for-net-apps"></a>Creare i file di risorse per le app .NET

È possibile includere risorse, ad esempio stringhe, immagini o dati di oggetti, all'interno di file di risorse per renderli facilmente disponibili per l'applicazione. In .NET Framework è possibile creare file di risorse in cinque modi diversi:

- Creare un file di testo contenente risorse stringa. È possibile usare il [generatore di file di risorse (Resgen.exe)](../tools/resgen-exe-resource-file-generator.md) per convertire il file di testo in un file di risorse binario con estensione resources. È quindi possibile incorporare il file di risorse binario in un eseguibile dell'applicazione o in una libreria di applicazioni usando un compilatore di linguaggio oppure è possibile incorporarlo in un assembly satellite tramite [assembly linker (Al.exe)](../tools/al-exe-assembly-linker.md). Per altre informazioni, vedere la sezione [Risorse in file di testo](creating-resource-files-for-desktop-apps.md#TextFiles).

- Creare un file di risorse XML con estensione resx contenente stringhe, immagini o dati di oggetto. È possibile usare il [generatore di file di risorse (Resgen.exe)](../tools/resgen-exe-resource-file-generator.md) per convertire il file con estensione resx in un file di risorse binario con estensione resources. È quindi possibile incorporare il file di risorse binario in un file eseguibile o in una libreria dell'applicazione tramite un compilatore del linguaggio. In alternativa, è possibile incorporare il file di risorse in un assembly satellite tramite [Assembly Linker (Al.exe)](../tools/al-exe-assembly-linker.md). Per altre informazioni, vedere la sezione [Risorse nei file con estensione resx](creating-resource-files-for-desktop-apps.md#ResxFiles).

- Creare un file di risorse XML con estensione resx a livello di codice usando tipi nello spazio dei nomi <xref:System.Resources>. È possibile creare un file con estensione resx, enumerarne le risorse e recuperare risorse specifiche in base al nome. Per altre informazioni, vedere [Uso dei file RESX a livello di codice](working-with-resx-files-programmatically.md).

- Creare un file di risorse binario con estensione resources a livello di codice. È quindi possibile incorporare il file in un file eseguibile o in una libreria dell'applicazione tramite un compilatore del linguaggio. In alternativa, è possibile incorporare il file di risorse in un assembly satellite tramite [Assembly Linker (Al.exe)](../tools/al-exe-assembly-linker.md). Per altre informazioni, vedere la sezione [Risorse in file con estensione resources](creating-resource-files-for-desktop-apps.md#ResourcesFiles).

- Usare [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) per creare un file di risorse e includerlo nel progetto. Visual Studio è dotato di un editor di risorse che consente di aggiungere, eliminare e modificare risorse. In fase di compilazione il file di risorse viene automaticamente convertito in un file binario con estensione resources e incorporato in un assembly dell'applicazione o in un assembly satellite. Per altre informazioni, vedere la sezione [File di risorse in Visual Studio](creating-resource-files-for-desktop-apps.md#VSResFiles).

<a name="TextFiles"></a>
## <a name="resources-in-text-files"></a>Risorse in file di testo

È possibile usare file di testo (con estensione txt o restext) per archiviare solo risorse stringa. Per le risorse non di tipo stringa, usare file con estensione resx o crearle a livello di codice. I file di testo che contengono risorse stringa hanno il formato seguente:

```text
# This is an optional comment.
name = value

; This is another optional comment.
name = value

; The following supports conditional compilation if X is defined.
#ifdef X
name1=value1
name2=value2
#endif

# The following supports conditional compilation if Y is undefined.
#if !Y
name1=value1
name2=value2
#endif
```

 Il formato dei file di risorse con estensione txt e restext è identico. L'estensione restext serve semplicemente a rendere immediatamente identificabili i file di testo come file di risorse basati su testo.

 Le risorse stringa sono visualizzate come coppie *name/value*, dove *name* è una stringa che identifica la risorsa e *value* è la stringa di risorsa che viene restituita quando si passa *name* a un metodo di recupero quale <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType>. *name* e *value* devono essere separati da un segno di uguale (=). ad esempio:

```text
FileMenuName=File
EditMenuName=Edit
ViewMenuName=View
HelpMenuName=Help
```

> [!CAUTION]
> Non usare file di risorse per archiviare password, informazioni sensibili per la sicurezza o dati personali.

 Stringhe vuote, ovvero risorse il cui valore è <xref:System.String.Empty?displayProperty=nameWithType>, sono consentite nei file di testo. ad esempio:

```text
EmptyString=
```

 A partire da .NET Framework 4,5 e in tutte le versioni di .NET Core, i file di testo supportano la compilazione condizionale con i costrutti symbol.. `#ifdef` *symbol*. `#endif` e `#if !` *Symbol*... `#endif` . È quindi possibile usare l'opzione `/define` con il [generatore di file di risorse (Resgen.exe)](../tools/resgen-exe-resource-file-generator.md) per definire i simboli. Ogni risorsa richiede un costrutto symbol... `#ifdef` *symbol* `#endif` o `#if !` *Symbol*.. `#endif` .. Se si usa un'istruzione `#ifdef` e *simbolo* è definito, la risorsa associata è inclusa nel file con estensione resources. In caso contrario, non è inclusa. Se si usa un'istruzione `#if !` e *simbolo* non è definito, la risorsa associata è inclusa nel file con estensione resources. In caso contrario, non è inclusa.

 Nei file di testo i commenti sono facoltativi e sono preceduti da un punto e virgola (;) o da un segno di cancelletto (#) all'inizio della riga. Le righe che contengono i commenti possono trovarsi in qualsiasi punto del file. I commenti non sono inclusi in un file con estensione resources compilato creato tramite il [generatore di file di risorse (Resgen.exe)](../tools/resgen-exe-resource-file-generator.md).

 Eventuali righe vuote nel file di testo sono considerate spazi e vengono ignorate.

 Nell'esempio seguente sono definite due risorse stringa denominate `OKButton` e `CancelButton`.

```text
#Define resources for buttons in the user interface.
OKButton=OK
CancelButton=Cancel
```

 Se il file di testo contiene occorrenze duplicate di *name*, il [generatore di file di risorse (Resgen.exe)](../tools/resgen-exe-resource-file-generator.md) visualizza un avviso e ignora il secondo nome.

 il *valore* non può contenere caratteri di nuova riga, ma è possibile usare caratteri di escape in stile linguaggio C, ad esempio `\n` per rappresentare una nuova riga e `\t` per rappresentare una scheda. È anche possibile includere un carattere barra rovesciata se è preceduto da un carattere di escape, ad esempio " \\ \\ ". Sono anche consentite le stringhe vuote.

 Salvare le risorse in formato di file di testo usando la codifica UTF-8 o la codifica UTF-16 nell'ordine dei byte little-endian o big-endian. Il [generatore di file di risorse (Resgen.exe)](../tools/resgen-exe-resource-file-generator.md), tuttavia, che consente di convertire un file con estensione txt in un file con estensione resources, per impostazione predefinita considera i file come salvati con la codifica UTF-8. Se si vuole che Resgen.exe riconosca un file come salvato con la codifica UTF-16, è necessario includere un byte order mark Unicode (U + FEFF) all'inizio del file.

 Per incorporare un file di risorse in formato testo in un assembly .NET, è necessario convertire il file in un file di risorse binario (con estensione resources) tramite il [generatore di file di risorse (Resgen.exe)](../tools/resgen-exe-resource-file-generator.md). È quindi possibile incorporare il file con estensione resources in un assembly .NET tramite un compilatore del linguaggio. In alternativa, è possibile incorporare il file in un assembly satellite tramite [Assembly Linker (Al.exe)](../tools/al-exe-assembly-linker.md).

 Nell'esempio seguente viene usato un file di risorse in formato testo denominato GreetingResources.txt per un'applicazione console "Hello World" semplice. Il file di testo definisce due stringhe, `prompt` e `greeting` , che richiedono all'utente di immettere il proprio nome e visualizzare un messaggio di saluto.

```text
# GreetingResources.txt
# A resource file in text format for a "Hello World" application.
#
# Initial prompt to the user.
prompt=Enter your name:
# Format string to display the result.
greeting=Hello, {0}!
```

Il file di testo viene convertito in un file con estensione resources tramite il comando seguente:

```console
resgen GreetingResources.txt
```

 Nell'esempio seguente viene illustrato il codice sorgente per un'applicazione console che usa il file con estensione resources per visualizzare messaggi per l'utente.

 [!code-csharp[Conceptual.Resources.TextFiles#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.textfiles/cs/greeting.cs#1)]
 [!code-vb[Conceptual.Resources.TextFiles#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.textfiles/vb/greeting.vb#1)]

 Se si usa Visual Basic e il file di codice sorgente è denominato Greeting.vb, il comando seguente crea un file eseguibile che include il file con estensione resources incorporato:

```console
vbc greeting.vb -resource:GreetingResources.resources
```

 Se si usa C# e il file di codice sorgente è denominato Greeting.cs, il comando seguente crea un file eseguibile che include il file con estensione resources incorporato:

```console
csc greeting.cs -resource:GreetingResources.resources
```

<a name="ResxFiles"></a>
## <a name="resources-in-resx-files"></a>Risorse nei file con estensione resx
 A differenza dei file di testo, che possono archiviare solo risorse stringa, i file di risorse XML con estensione resx possono archiviare stringhe, dati binari quali immagini, icone e clip audio e oggetti a livello di codice. Un file con estensione resx contiene un'intestazione standard che descrive il formato delle voci di risorsa e specifica le informazioni del controllo delle versioni per l'XML usato per l'analisi dei dati. I dati del file di risorse seguono l'intestazione XML. Ogni elemento di dati è costituito da una coppia nome/valore contenuta in un tag `data`. Il relativo attributo `name` definisce il nome della risorsa e il tag `value` annidato contiene il valore della risorsa stessa. Per i dati di tipo stringa, il tag `value` contiene la stringa.

 Il tag `data` seguente, ad esempio, definisce una risorsa stringa denominata `prompt` il cui valore è "Enter your name:".

```xml
<data name="prompt" xml:space="preserve">
  <value>Enter your name:</value>
</data>
```

> [!WARNING]
> Non usare file di risorse per archiviare password, informazioni sensibili per la sicurezza o dati personali.

 Per gli oggetti risorsa, il tag **dati** include un attributo `type` che indica il tipo di dati della risorsa. Per gli oggetti costituiti da dati binari, il tag `data` include anche un attributo `mimetype`, che indica il tipo `base64` dei dati binari.

> [!NOTE]
> Tutti i file con estensione resx usano un formattatore di serializzazione binario per generare e analizzare i dati binari relativi a un tipo specifico. Di conseguenza, un file con estensione resx può perdere di validità se il formato di serializzazione binario di un oggetto diventa incompatibile.

 Nell'esempio seguente viene illustrata una parte di un file con estensione resx che include una risorsa <xref:System.Int32> e un'immagine bitmap.

```xml
<data name="i1" type="System.Int32, mscorlib">
  <value>20</value>
</data>

<data name="flag" type="System.Drawing.Bitmap, System.Drawing,
    Version=1.0.5000.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a"
    mimetype="application/x-microsoft.net.object.bytearray.base64">
  <value>
    AAEAAAD/////AQAAAAAAAAAMAgAAADtTeX…
  </value>
</data>
```

> [!IMPORTANT]
> Poiché i file con estensione resx devono essere costituiti da codice XML ben formato in un formato predefinito, non è consigliabile usare i file con estensione resx manualmente, specialmente se tali file contengono risorse diverse da stringhe. [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) offre invece un'interfaccia trasparente per la creazione e la modifica di file con estensione resx. Per altre informazioni, vedere la sezione [File di risorse in Visual Studio](creating-resource-files-for-desktop-apps.md#VSResFiles). È anche possibile creare e modificare i file con estensione resx a livello di codice. Per altre informazioni, vedere [Uso dei file RESX a livello di codice](working-with-resx-files-programmatically.md).

<a name="ResourcesFiles"></a>
## <a name="resources-in-resources-files"></a>Risorse nei file con estensione resources

È possibile usare la classe <xref:System.Resources.ResourceWriter?displayProperty=nameWithType> per creare a livello di codice un file di risorse binario con estensione resources direttamente dal codice. È anche possibile usare il [generatore di file di risorse (Resgen.exe)](../tools/resgen-exe-resource-file-generator.md) per creare un file con estensione resources da un file di testo o da un file con estensione resx. Oltre a dati di tipo stringa, il file con estensione resources può contenere dati binari (matrici di byte) e dati di oggetto. Per creare un file con estensione resources a livello di codice è necessaria la procedura seguente:

1. Creare un oggetto <xref:System.Resources.ResourceWriter> con un nome file univoco. A tale scopo, specificare un nome file o un flusso di file per un costruttore della classe <xref:System.Resources.ResourceWriter>.

2. Chiamare uno degli overload del metodo <xref:System.Resources.ResourceWriter.AddResource%2A?displayProperty=nameWithType> per ogni risorsa denominata da aggiungere al file. La risorsa può essere una stringa, un oggetto o una raccolta di dati binari (una matrice di byte).

3. Chiamare il metodo <xref:System.Resources.ResourceWriter.Close%2A?displayProperty=nameWithType> per scrivere le risorse nel file e chiudere l'oggetto <xref:System.Resources.ResourceWriter>.

> [!NOTE]
> Non usare file di risorse per archiviare password, informazioni sensibili per la sicurezza o dati personali.

 Nell'esempio seguente viene creato a livello di codice un file con estensione resources denominato CarResources.resources contenente sei stringhe, un'icona e due oggetti definiti dall'applicazione, ovvero due oggetti `Automobile`. La `Automobile` classe, che viene definita e di cui viene creata un'istanza nell'esempio, viene contrassegnata con l' <xref:System.SerializableAttribute> attributo, che consente di renderla permanente dal formattatore di serializzazione binaria.

 [!code-csharp[Conceptual.Resources.Resources#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.resources/cs/resources1.cs#1)]
 [!code-vb[Conceptual.Resources.Resources#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.resources/vb/resources1.vb#1)]

 Dopo aver creato il file con estensione resources, è possibile incorporarlo in un eseguibile di runtime o in una libreria, includendo l'opzione `/resource` del compilatore del linguaggio, oppure in un assembly satellite tramite [Assembly Linker (Al.exe)](../tools/al-exe-assembly-linker.md).

<a name="VSResFiles"></a>
## <a name="resource-files-in-visual-studio"></a>File di risorse in Visual Studio

Quando si aggiunge un file di risorse a un progetto di [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link), Visual Studio crea un file con estensione resx nella directory del progetto. In Visual Studio sono disponibili editor di risorse che consentono di aggiungere stringhe, immagini e oggetti binari. Poiché gli editor vengono progettati per gestire solo dati statici, non possono essere usati per archiviare oggetti a livello di codice, ma è necessario scrivere i dati degli oggetti in un file con estensione resx o resources a livello di codice. Per altre informazioni, vedere [Uso dei file RESX a livello di codice](working-with-resx-files-programmatically.md) e la sezione [Risorse in file con estensione resources](creating-resource-files-for-desktop-apps.md#ResourcesFiles).

Se si aggiungono risorse localizzate, assegnarvi lo stesso nome di file radice del file di risorse principale. È necessario designare anche le impostazioni cultura nel nome del file. Se ad esempio si aggiunge un file di risorse denominato Resources.resx, è possibile creare anche file di risorse denominati Resources.en-US.resx e Resources.fr-FR.resx per le risorse localizzate rispettivamente per le impostazioni cultura inglesi (Stati Uniti) e francesi (Francia). È necessario designare anche le impostazioni cultura predefinite dell'applicazione. Si tratta delle impostazioni cultura di cui si usano le risorse se non è possibile trovare le risorse localizzate per impostazioni cultura particolari. Per specificare le impostazioni cultura predefinite, in Esplora soluzioni in Visual Studio fare clic con il pulsante destro del mouse sul nome del progetto, scegliere Applicazione, fare clic su **Informazioni assembly**e selezionare la lingua e le impostazioni cultura appropriate nell'elenco **Lingua neutra**.

In fase di compilazione, Visual Studio prima converte i file con estensione resx di un progetto in file di risorse binari con estensione resources e li archivia in una sottodirectory della directory *obj* del progetto. Visual Studio incorpora ogni file di risorse che non contiene risorse localizzate nell'assembly principale generato dal progetto. Se tutti i file di risorse contengono risorse localizzate, Visual Studio li incorpora in assembly satellite separati per ognuna delle impostazioni cultura localizzate e archivia quindi ogni assembly satellite in una directory il cui nome corrisponde alle impostazioni cultura localizzate. Ad esempio, le risorse localizzate per l'inglese (Stati Uniti) vengono archiviate in un assembly satellite nella sottodirectory en-US.

## <a name="see-also"></a>Vedi anche

- <xref:System.Resources>
- [Risorse nelle applicazioni desktop](index.md)
- [Packaging and Deploying Resources](packaging-and-deploying-resources-in-desktop-apps.md)
