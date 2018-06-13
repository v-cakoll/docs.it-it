---
title: Dati e oggetti dati
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data transfer [WPF], drag-and-drop
- DataFormats class [WPF]
- DataObject class [WPF]
ms.assetid: 5967d557-1867-420f-a524-ae3af78402da
ms.openlocfilehash: ff596dc7428c9d105a27999f216d33e735e35a22
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33540319"
---
# <a name="data-and-data-objects"></a>Dati e oggetti dati
I dati trasferiti come parte di un'operazione di trascinamento e rilascio viene archiviati in un oggetto dati.  Concettualmente, un oggetto dati è costituito da uno o più delle seguenti coppie di:  
  
-   Un <xref:System.Object> che contiene i dati effettivi.  
  
-   Un identificatore di formato di dati corrispondente.  
  
 I dati stessi possono contenere qualsiasi elemento che può essere rappresentato come una base <xref:System.Object>.  Il formato di dati corrispondente è una stringa o <xref:System.Type> che fornisce un hint sul formato dei dati è in.  Gli oggetti dati supportano l'hosting di più coppie di formato di dati o dati; In questo modo un singolo oggetto dati fornire i dati in più formati.  
  
<a name="Data_and_Data_Objects"></a>   
## <a name="data-objects"></a>Oggetti dati  
 Tutti gli oggetti di dati devono implementare il <xref:System.Windows.IDataObject> interfaccia che fornisce il seguente set standard di metodi che consentono e semplificano il trasferimento dei dati.  
  
|Metodo|Riepilogo|  
|------------|-------------|  
|<xref:System.Windows.IDataObject.GetData%2A>|Recupera un oggetto dati in un formato dati specificato.|  
|<xref:System.Windows.IDataObject.GetDataPresent%2A>|Controlla se i dati sono disponibili in, o possono essere convertiti nel formato specificato.|  
|<xref:System.Windows.IDataObject.GetFormats%2A>|Restituisce un elenco di formati di dati nell'oggetto dati viene archiviati in, o possono essere convertiti in.|  
|<xref:System.Windows.IDataObject.SetData%2A>|Archivia i dati specificati nell'oggetto dati.|  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fornisce un'implementazione di base di <xref:System.Windows.IDataObject> nella <xref:System.Windows.DataObject> classe. L'azione <xref:System.Windows.DataObject> classe è sufficiente per molti scenari comuni di trasferimento dei dati.  
  
 Esistono vari formati predefiniti, quali bitmap, CSV, file, HTML, RTF, stringa, testo e audio. Per informazioni sui formati di dati predefiniti forniti con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], vedere il <xref:System.Windows.DataFormats> argomento di riferimento di classe.  
  
 Oggetti dati è in genere includono una funzionalità per convertire automaticamente i dati archiviati in un formato in un formato diverso durante l'estrazione dei dati. Questa funzionalità è detta automaticamente la conversione. Quando si eseguono query per i formati di dati disponibili in un oggetto dati, i formati di dati convertibili automaticamente possono essere filtrati da formati dati nativi chiamando il <xref:System.Windows.DataObject.GetFormats%28System.Boolean%29> o <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> metodo e specificando la `autoConvert` parametro come `false`.  Quando si aggiungono dati a un oggetto dati con il <xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%2CSystem.Boolean%29> (metodo), la conversione automatica dei dati può essere impedita impostando il `autoConvert` parametro `false`.  
  
<a name="Working_with_Data_Objects"></a>   
## <a name="working-with-data-objects"></a>Utilizzo di oggetti dati  
 Questa sezione descrive le tecniche comuni per la creazione e utilizzo di oggetti dati.  
  
### <a name="creating-new-data-objects"></a>Creazione di nuovi oggetti di dati  
 Il <xref:System.Windows.DataObject> classe fornisce molti costruttori di overload che agevolano la compilazione di un nuovo <xref:System.Windows.DataObject> istanza con una coppia di formato singolo dati.  
  
 Esempio di codice seguente crea un nuovo oggetto dati e viene utilizzato uno dei costruttori di overload <xref:System.Windows.DataObject.%23ctor%2A>(<xref:System.Windows.DataObject.%23ctor(System.String,System.Object)>) per inizializzare l'oggetto dati con una stringa e un formato dati specificato.  In questo caso, il formato di dati è specificato da una stringa. la <xref:System.Windows.DataFormats> classe fornisce un set di stringhe di tipo predefinite. Per impostazione predefinita, è consentita la conversione automatica dei dati archiviati.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring)]  
  
 Per ulteriori esempi di codice che crea un oggetto dati, vedere [creare un oggetto dati](../../../../docs/framework/wpf/advanced/how-to-create-a-data-object.md).  
  
### <a name="storing-data-in-multiple-formats"></a>L'archiviazione dei dati in più formati  
 Un singolo oggetto dati è in grado di archiviare dati in più formati.   L'utilizzo di più formati di dati all'interno di un singolo oggetto dati strategico potenzialmente rende l'oggetto dati utilizzabile da un'ampia gamma di obiettivi di rilascio più se solo un unico formato dati potrebbe essere rappresentato.  Si noti che, in generale, un'origine di trascinamento deve essere indipendente sui formati di dati che possono essere utilizzati da potenziali obiettivi di rilascio.  
  
 Nell'esempio seguente viene illustrato come utilizzare il <xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%29> metodo per aggiungere dati a un oggetto dati in più formati.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_storemultipleformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_storemultipleformats)]  
  
### <a name="querying-a-data-object-for-available-formats"></a>Esecuzione di query su un oggetto dati per i formati disponibili  
 Poiché un singolo oggetto dati può contenere un numero arbitrario di formati di dati, oggetti dati consentono di recuperare un elenco dei formati di dati disponibili.  
  
 Il codice di esempio seguente usa il <xref:System.Windows.DataObject.GetFormats%2A> overload per ottenere una matrice di stringhe che indica tutti i formati di dati disponibili in un oggetto dati (nativo e conversione automatica).  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats)]  
  
 Per ulteriori esempi di codice che esegue una query di un oggetto dati per i formati dati disponibili, vedere [sono elencati i formati di dati in un oggetto dati](../../../../docs/framework/wpf/advanced/how-to-list-the-data-formats-in-a-data-object.md).  Per esempi di query su un oggetto dati per la presenza di un particolare formato dati, vedere [determinare se un formato di dati è presente in un oggetto dati](../../../../docs/framework/wpf/advanced/how-to-determine-if-a-data-format-is-present-in-a-data-object.md).  
  
### <a name="retrieving-data-from-a-data-object"></a>Il recupero dei dati da un oggetto dati  
 Il recupero dei dati da un oggetto dati in un determinato formato richiede semplicemente la chiamata a uno del <xref:System.Windows.DataObject.GetData%2A> metodi e specificare il formato di dati desiderato.  Uno del <xref:System.Windows.DataObject.GetDataPresent%2A> metodi possono essere usati per verificare la presenza di un particolare formato dati.  <xref:System.Windows.DataObject.GetData%2A> Restituisce i dati in un <xref:System.Object>; a seconda del formato di dati, questo oggetto può essere convertito in un contenitore specifico del tipo.  
  
 Il codice di esempio seguente usa il <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> overload per controllare se un formato dati specificato è disponibile (nativa o mediante conversione automatica). Se il formato specificato non è disponibile, l'esempio recupera i dati utilizzando il <xref:System.Windows.DataObject.GetData%28System.String%29> metodo.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat)]  
  
 Per ulteriori esempi di codice che recupera dati da un oggetto dati, vedere [recupera i dati in un determinato formato di dati](../../../../docs/framework/wpf/advanced/how-to-retrieve-data-in-a-particular-data-format.md).  
  
### <a name="removing-data-from-a-data-object"></a>Rimozione dei dati da un oggetto dati  
 Impossibile rimuovere dati direttamente da un oggetto dati.  Per rimuovere in modo efficace i dati da un oggetto dati, seguire questi passaggi:  
  
1.  Creare un nuovo oggetto dati che conterrà solo i dati di cui che si desidera mantenere.  
  
2.  "Copia" i dati desiderati dall'oggetto dati precedente al nuovo oggetto dati.  Per copiare i dati, utilizzare uno del <xref:System.Windows.DataObject.GetData%2A> metodi per recuperare un <xref:System.Object> che contiene i dati non elaborati e quindi utilizzare uno del <xref:System.Windows.DataObject.SetData%2A> metodi per aggiungere i dati al nuovo oggetto dati.  
  
3.  Sostituire l'oggetto dati precedente con quello nuovo.  
  
> [!NOTE]
>  Il <xref:System.Windows.DataObject.SetData%2A> metodi consentono solo di aggiungere dati a un oggetto dati; non sostituiscono i dati, anche se i dati e il formato dei dati sono esattamente uguali come una chiamata precedente. La chiamata <xref:System.Windows.DataObject.SetData%2A> due volte per gli stessi dati e dati formato comporterà il formato di dati/presenti due volte nell'oggetto dati.
