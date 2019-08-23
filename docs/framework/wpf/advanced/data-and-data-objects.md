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
ms.openlocfilehash: 4b948a64a14df7ea79b54b810f734056d57ef406
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964857"
---
# <a name="data-and-data-objects"></a>Dati e oggetti dati
I dati trasferiti come parte di un'operazione di trascinamento della selezione vengono archiviati in un oggetto dati.  Concettualmente, un oggetto dati è costituito da una o più delle coppie seguenti:  
  
- Oggetto <xref:System.Object> che contiene i dati effettivi.  
  
- Identificatore del formato dati corrispondente.  
  
 I dati possono essere costituiti da qualsiasi elemento che può essere rappresentato come <xref:System.Object>base.  Il formato dei dati corrispondente è una stringa <xref:System.Type> o che fornisce un suggerimento sul formato in cui si trovano i dati.  Gli oggetti dati supportano l'hosting di più coppie di formato dati/dati; Ciò consente a un singolo oggetto dati di fornire dati in più formati.  
  
<a name="Data_and_Data_Objects"></a>   
## <a name="data-objects"></a>Oggetti dati  
 Tutti gli oggetti dati devono implementare <xref:System.Windows.IDataObject> l'interfaccia, che fornisce il set di metodi standard seguente che consentono e facilitano il trasferimento dei dati.  
  
|Metodo|Riepilogo|  
|------------|-------------|  
|<xref:System.Windows.IDataObject.GetData%2A>|Recupera un oggetto dati in un formato dati specificato.|  
|<xref:System.Windows.IDataObject.GetDataPresent%2A>|Verifica se i dati sono disponibili in o possono essere convertiti in un formato specificato.|  
|<xref:System.Windows.IDataObject.GetFormats%2A>|Restituisce un elenco di formati in cui i dati in questo oggetto dati sono archiviati o possono essere convertiti in.|  
|<xref:System.Windows.IDataObject.SetData%2A>|Archivia i dati specificati in questo oggetto dati.|  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]fornisce un'implementazione di base <xref:System.Windows.IDataObject> di <xref:System.Windows.DataObject> nella classe. La classe <xref:System.Windows.DataObject> Stock è sufficiente per molti scenari comuni di trasferimento dei dati.  
  
 Sono disponibili diversi formati predefiniti, ad esempio bitmap, CSV, file, HTML, RTF, stringhe, testo e audio. Per informazioni sui formati di dati predefiniti forniti con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], vedere l'argomento di riferimento alla <xref:System.Windows.DataFormats> classe.  
  
 Gli oggetti dati includono in genere una funzionalità per la conversione automatica dei dati archiviati in un formato diverso, durante l'estrazione dei dati; Questa funzionalità viene definita conversione automatica. Quando si eseguono query per i formati di dati disponibili in un oggetto dati, è possibile filtrare i formati di dati convertibili automaticamente dai formati di <xref:System.Windows.DataObject.GetFormats%28System.Boolean%29> dati <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> nativi chiamando il metodo `autoConvert` o e `false`specificando il parametro come.  Quando si aggiungono dati a un oggetto dati <xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%2CSystem.Boolean%29> con il metodo, la conversione automatica dei dati può essere proibita `autoConvert` impostando `false`il parametro su.  
  
<a name="Working_with_Data_Objects"></a>   
## <a name="working-with-data-objects"></a>Utilizzo di oggetti dati  
 In questa sezione vengono descritte le tecniche comuni per la creazione e l'utilizzo di oggetti dati.  
  
### <a name="creating-new-data-objects"></a>Creazione di nuovi oggetti dati  
 La <xref:System.Windows.DataObject> classe fornisce diversi costruttori di overload che facilitano il popolamento di una <xref:System.Windows.DataObject> nuova istanza con una singola coppia dati/formato dati.  
  
 Nell'esempio di codice seguente viene creato un nuovo oggetto dati e viene utilizzato uno dei costruttori <xref:System.Windows.DataObject.%23ctor%2A>di overload (<xref:System.Windows.DataObject.%23ctor(System.String,System.Object)>) per inizializzare l'oggetto dati con una stringa e un formato dati specificato.  In questo caso, il formato dati è specificato da una stringa. la <xref:System.Windows.DataFormats> classe fornisce un set di stringhe di tipo predefinite. La conversione automatica dei dati archiviati è consentita per impostazione predefinita.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring)]  
  
 Per altri esempi di codice per la creazione di un oggetto dati, vedere [creare un oggetto dati](how-to-create-a-data-object.md).  
  
### <a name="storing-data-in-multiple-formats"></a>Archiviazione dei dati in più formati  
 Un singolo oggetto dati è in grado di archiviare i dati in più formati.   L'uso strategico di più formati di dati all'interno di un singolo oggetto dati potenzialmente rende l'oggetto dati utilizzabile da una varietà più ampia di destinazioni di rilascio rispetto a quando è possibile rappresentare solo un singolo formato di dati.  Si noti che, in generale, un'origine di trascinamento deve essere indipendente dai formati di dati che possono essere utilizzati da potenziali destinazioni di rilascio.  
  
 Nell'esempio seguente viene illustrato come utilizzare il <xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%29> metodo per aggiungere dati a un oggetto dati in più formati.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_storemultipleformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_storemultipleformats)]  
  
### <a name="querying-a-data-object-for-available-formats"></a>Esecuzione di query su un oggetto dati per i formati disponibili  
 Poiché un singolo oggetto dati può contenere un numero arbitrario di formati di dati, gli oggetti dati includono le funzionalità per il recupero di un elenco di formati di dati disponibili.  
  
 Il codice di esempio seguente usa <xref:System.Windows.DataObject.GetFormats%2A> l'overload per ottenere una matrice di stringhe che indica tutti i formati di dati disponibili in un oggetto dati (sia nativi che tramite conversione automatica).  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats)]  
  
 Per altri esempi di codice che esegue query su un oggetto dati per i formati di dati disponibili, vedere [elencare i formati di dati in un oggetto dati](how-to-list-the-data-formats-in-a-data-object.md).  Per esempi di esecuzione di query su un oggetto dati per la presenza di un particolare formato dati, vedere [determinare se un formato di dati è presente in un oggetto dati](how-to-determine-if-a-data-format-is-present-in-a-data-object.md).  
  
### <a name="retrieving-data-from-a-data-object"></a>Recupero di dati da un oggetto dati  
 Il recupero di dati da un oggetto dati in un particolare formato prevede semplicemente la chiamata a <xref:System.Windows.DataObject.GetData%2A> uno dei metodi e la specifica del formato dati desiderato.  Uno dei <xref:System.Windows.DataObject.GetDataPresent%2A> metodi può essere utilizzato per verificare la presenza di un particolare formato dati.  <xref:System.Windows.DataObject.GetData%2A>Restituisce i dati in un <xref:System.Object>oggetto; a seconda del formato dati, è possibile eseguire il cast di questo oggetto a un contenitore specifico del tipo.  
  
 Nell'esempio di codice seguente viene <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> utilizzato l'overload per verificare se è disponibile un formato dati specificato (nativo o tramite conversione automatica). Se il formato specificato è disponibile, nell'esempio vengono recuperati i dati utilizzando <xref:System.Windows.DataObject.GetData%28System.String%29> il metodo.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat)]  
  
 Per altri esempi di codice che recupera dati da un oggetto dati, vedere [recuperare dati in un particolare formato dati](how-to-retrieve-data-in-a-particular-data-format.md).  
  
### <a name="removing-data-from-a-data-object"></a>Rimozione di dati da un oggetto dati  
 I dati non possono essere rimossi direttamente da un oggetto dati.  Per rimuovere efficacemente i dati da un oggetto dati, attenersi alla procedura seguente:  
  
1. Creare un nuovo oggetto dati che conterrà solo i dati che si desidera mantenere.  
  
2. "Copiare" i dati desiderati dall'oggetto dati precedente al nuovo oggetto dati.  Per copiare i dati, utilizzare uno dei <xref:System.Windows.DataObject.GetData%2A> metodi per recuperare un <xref:System.Object> oggetto che contiene i dati non elaborati, <xref:System.Windows.DataObject.SetData%2A> quindi utilizzare uno dei metodi per aggiungere i dati al nuovo oggetto dati.  
  
3. Sostituire l'oggetto dati precedente con quello nuovo.  
  
> [!NOTE]
> I <xref:System.Windows.DataObject.SetData%2A> metodi aggiungono solo dati a un oggetto dati, ma non sostituiscono i dati, anche se i dati e il formato dati sono esattamente uguali a quelli di una chiamata precedente. La <xref:System.Windows.DataObject.SetData%2A> chiamata di due volte per gli stessi dati e il formato dati comporterà la presenza del formato dati/dati due volte nell'oggetto dati.
