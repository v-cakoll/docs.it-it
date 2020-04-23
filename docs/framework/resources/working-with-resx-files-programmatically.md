---
title: Uso dei file RESX a livello di codice
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- resource files, .resx files
- .resx files
ms.assetid: 168f941a-2b84-43f8-933f-cf4a8548d824
ms.openlocfilehash: 3b84d77e4ac9b9889d1bc2f08e5ead6b81deecb0
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2020
ms.locfileid: "81243037"
---
# <a name="work-with-resx-files-programmatically"></a>Usare i file con estensione resx a livello di codice

Poiché i file di risorse XML (con estensione resx) devono essere costituiti da codice XML ben definito, comprensivo di un'intestazione che deve seguire uno schema specifico, seguita da dati in coppie nome/valore, la creazione manuale di questi file è soggetta a errori. In alternativa, è possibile creare file con estensione resx a livello di codice usando tipi e membri inclusi nella libreria di classi .NET. La libreria di classi .NET può essere usata anche per recuperare risorse archiviate in file con estensione resx. Questo articolo illustra come usare i tipi e i membri nello <xref:System.Resources> spazio dei nomi per lavorare con i file resx.

Questo articolo illustra l'uso di file XML (con estensione resx) che contengono risorse. Per informazioni sull'utilizzo di file di risorse binari che sono stati incorporati negli assembly <xref:System.Resources.ResourceManager>, vedere.

> [!WARNING]
> Esistono anche modi per usare i file RESX, oltre all'uso a livello di codice. Quando si aggiunge un file di risorse a un progetto di [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) , Visual Studio fornisce un'interfaccia per la creazione e la gestione di un file resx e converte automaticamente il file con estensione resx in un file con estensione resources in fase di compilazione. È anche possibile usare un editor di testo per modificare direttamente un file RESX. Prestare comunque attenzione a non modificare le eventuali informazioni binarie archiviate nel file, per evitare di danneggiarlo.

## <a name="create-a-resx-file"></a>Creare un file con estensione resx

È possibile usare la classe <xref:System.Resources.ResXResourceWriter?displayProperty=nameWithType> per creare un file RESX a livello di codice seguendo questa procedura:

1. Creare un'istanza di un oggetto <xref:System.Resources.ResXResourceWriter> chiamando il metodo <xref:System.Resources.ResXResourceWriter.%23ctor%28System.String%29> e specificando il nome del file RESX. Il nome del file deve includere l'estensione resx. Se si crea un'istanza dell'oggetto <xref:System.Resources.ResXResourceWriter> in un blocco `using` , non è necessario chiamare esplicitamente il metodo <xref:System.Resources.ResXResourceWriter.Close%2A?displayProperty=nameWithType> nel passaggio 3.

2. Chiamare il metodo <xref:System.Resources.ResXResourceWriter.AddResource%2A?displayProperty=nameWithType> per ogni risorsa da aggiungere al file. Usare l'overload di questo metodo per aggiungere dati stringa, oggetto e binari (matrice di byte). Se la risorsa è un oggetto, deve essere serializzabile.

3. Chiamare il metodo <xref:System.Resources.ResXResourceWriter.Close%2A?displayProperty=nameWithType> per generare il file di risorse e per rilasciare tutte le risorse. Se l'oggetto <xref:System.Resources.ResXResourceWriter> è stato creato all'interno di un blocco `using` , le risorse vengono scritte nel file RESX e le risorse usate dall'oggetto <xref:System.Resources.ResXResourceWriter> vengono rilasciate alla fine del blocco `using` .

Il file RESX risultante ha l'intestazione appropriata e un tag `data` per ogni risorsa aggiunta dal metodo <xref:System.Resources.ResXResourceWriter.AddResource%2A?displayProperty=nameWithType> .

> [!WARNING]
> Non usare file di risorse per archiviare password, informazioni sensibili per la sicurezza o dati personali.

Nell'esempio seguente viene creato un file con estensione resx denominato CarResources.resx che archivia sei stringhe, un'icona e due oggetti definiti dall'applicazione, ovvero due oggetti `Automobile` . La `Automobile` classe, che viene definita e di cui viene creata un'istanza nell'esempio, viene <xref:System.SerializableAttribute> contrassegnata con l'attributo.

[!code-csharp[Conceptual.Resources.ResX#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.resx/cs/create1.cs#1)]
[!code-vb[Conceptual.Resources.ResX#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.resx/vb/create1.vb#1)]

> [!TIP]
> È anche possibile usare [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) per creare file con estensione resx. In fase di compilazione Visual Studio usa il [generatore di file di risorse (Resgen.exe)](../tools/resgen-exe-resource-file-generator.md) per convertire il file RESX in una risorsa binaria (con estensione resources) e lo incorpora anche nell'assembly dell'applicazione o in un assembly satellite.

Non è possibile incorporare un file RESX in un eseguibile di runtime o compilarlo in un assembly satellite. Il file RESX deve essere convertito in un file di risorse binario (con estensione resources) usando il [generatore di file di risorse (Resgen.exe)](../tools/resgen-exe-resource-file-generator.md). Successivamente, il file con estensione resources risultante può essere incorporato in un assembly dell'applicazione o in un assembly satellite. Per altre informazioni, vedere [Creating Resource Files](creating-resource-files-for-desktop-apps.md).

## <a name="enumerate-resources"></a>Enumerare le risorse
 In alcuni casi può essere necessario recuperare tutte le risorse anziché una risorsa specifica da un file RESX. A questo scopo, si può usare la classe <xref:System.Resources.ResXResourceReader?displayProperty=nameWithType> , che fornisce un enumeratore per tutte le risorse nel file RESX. La classe <xref:System.Resources.ResXResourceReader?displayProperty=nameWithType> implementa <xref:System.Collections.IDictionaryEnumerator>, che restituisce un oggetto <xref:System.Collections.DictionaryEntry> che rappresenta una risorsa specifica per ogni iterazione del ciclo. La relativa proprietà <xref:System.Collections.DictionaryEntry.Key%2A?displayProperty=nameWithType> restituisce la chiave della risorsa e la proprietà <xref:System.Collections.DictionaryEntry.Value%2A?displayProperty=nameWithType> restituisce il valore della risorsa.

 L'esempio seguente consente di creare un oggetto <xref:System.Resources.ResXResourceReader> per il file CarResources.resx creato nell'esempio precedente e di scorrere il file di risorse. Aggiunge i due oggetti `Automobile` definiti nel file di risorse a un oggetto <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> e aggiunge cinque delle sei stringhe a un oggetto <xref:System.Collections.SortedList> . I valori nell'oggetto <xref:System.Collections.SortedList> vengono convertiti in una matrice di parametri, usata per visualizzare le intestazioni di colonna nella console. Nella console vengono visualizzati anche i valori della proprietà `Automobile` .

 [!code-csharp[Conceptual.Resources.ResX#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.resx/cs/enumerate1.cs#2)]
 [!code-vb[Conceptual.Resources.ResX#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.resx/vb/enumerate1.vb#2)]

## <a name="retrieve-a-specific-resource"></a>Recuperare una risorsa specifica
 Oltre a enumerare gli elementi in un file RESX, è possibile recuperare una risorsa specifica in base al nome tramite la classe <xref:System.Resources.ResXResourceSet?displayProperty=nameWithType> . Il metodo <xref:System.Resources.ResourceSet.GetString%28System.String%29?displayProperty=nameWithType> recupera il valore di una risorsa di tipo stringa denominata. Il metodo <xref:System.Resources.ResourceSet.GetObject%28System.String%29?displayProperty=nameWithType> recupera il valore di un oggetto denominato o di dati binari. Il metodo restituisce un oggetto di cui deve essere eseguito il cast (in C#) o da convertire (in Visual Basic) in un oggetto del tipo appropriato.

 L'esempio seguente recupera l'icona e la stringa della didascalia di un form in base ai nomi delle risorse corrispondenti. Recupera anche gli oggetti `Automobile` definiti dall'applicazione usati nell'esempio precedente e li visualizza in un controllo <xref:System.Windows.Forms.DataGridView>.

 [!code-csharp[Conceptual.Resources.ResX#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.resx/cs/retrieve1.cs#3)]
 [!code-vb[Conceptual.Resources.ResX#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.resx/vb/retrieve1.vb#3)]

## <a name="convert-resx-files-to-binary-resources-files"></a>Convertire i file RESX in file binari con estensione resources
 La conversione dei file RESX in file di risorse binari incorporati (con estensione resources) presenta vantaggi significativi. Sebbene i file RESX siano facili da leggere e gestire durante lo sviluppo di applicazioni, è raro che siano inclusi nelle applicazioni finite. Se vengono distribuiti con un'applicazione, sono costituiti da file separati indipendenti dall'eseguibile dell'applicazione e dalle librerie associate. Al contrario, i file con estensione resources sono incorporati nell'eseguibile dell'applicazione o negli assembly associati. Inoltre, per le applicazioni localizzate, se si basano su file RESX in fase di esecuzione la responsabilità della gestione del fallback delle risorse ricade sullo sviluppatore. Se invece è stato creato un set di assembly satellite che contengono i file con estensione resources incorporati, il processo di fallback delle risorse viene gestito da Common Language Runtime.

 Per convertire un file con estensione resx in un file con estensione resources, usare il [generatore di file di risorse (Resgen.exe)](../tools/resgen-exe-resource-file-generator.md), con la seguente sintassi di base:

 **Resgen.exe** *.resxNomeFile*

 Il risultato è un file di risorse binario con lo stesso nome file radice del file RESX e l'estensione resources. Questo file può quindi essere compilato in un file eseguibile o una libreria in fase di compilazione. Se si usa il compilatore Visual Basic, usare la sintassi seguente per incorporare un file con estensione resources nell'eseguibile di un'applicazione:

 **vbc** *filename* **.vb /resource:** *.resourcesFilename*

 Se si usa C#, la sintassi è la seguente:

 **csc** *filename* **.cs -resource:** *.resourcesFilename*

 Il file con estensione resources può essere incorporato in un assembly satellite anche tramite [Assembly Linker (AL.exe)](../tools/al-exe-assembly-linker.md), che ha la seguente sintassi di base:

 **al** *resourcesFilename* **-out:** *assemblyFilename*

## <a name="see-also"></a>Vedere anche

- [Creazione dei file di risorsa](creating-resource-files-for-desktop-apps.md)
- [Resgen. exe (Generatore di file di risorse)](../tools/resgen-exe-resource-file-generator.md)
- [Al. exe (assembly linker)](../tools/al-exe-assembly-linker.md)
