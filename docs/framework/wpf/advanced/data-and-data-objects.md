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
ms.openlocfilehash: 532c254f997da183b073ddc9e00b4364ecfcd739
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186341"
---
# <a name="data-and-data-objects"></a>Dati e oggetti dati
I dati trasferiti come parte di un'operazione di trascinamento della selezione vengono archiviati in un oggetto dati.  Concettualmente, un oggetto dati è costituito da una o più delle coppie seguenti:Conceptually, a data object consists of one or more of the following pairs:  
  
- Oggetto <xref:System.Object> che contiene i dati effettivi.  
  
- Identificatore del formato dati corrispondente.  
  
 I dati stessi possono essere costituiti da <xref:System.Object>tutto ciò che può essere rappresentato come base .  Il formato dati corrispondente <xref:System.Type> è una stringa o che fornisce un suggerimento sul formato dei dati.  Gli oggetti dati supportano l'hosting di più coppie di formato dati/dati; ciò consente a un singolo oggetto dati di fornire dati in più formati.  
  
<a name="Data_and_Data_Objects"></a>
## <a name="data-objects"></a>Oggetti dati  
 Tutti gli oggetti <xref:System.Windows.IDataObject> dati devono implementare l'interfaccia, che fornisce il seguente set standard di metodi che consentono e facilitano il trasferimento dei dati.  
  
|Metodo|Summary|  
|------------|-------------|  
|<xref:System.Windows.IDataObject.GetData%2A>|Recupera un oggetto dati in un formato dati specificato.|  
|<xref:System.Windows.IDataObject.GetDataPresent%2A>|Verifica se i dati sono disponibili o se possono essere convertiti in un formato specificato.|  
|<xref:System.Windows.IDataObject.GetFormats%2A>|Restituisce un elenco di formati in cui sono archiviati i dati di questo oggetto o in cui possono essere convertiti.|  
|<xref:System.Windows.IDataObject.SetData%2A>|Archivia i dati specificati in questo oggetto dati.|  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]fornisce un'implementazione di base di <xref:System.Windows.IDataObject> nella <xref:System.Windows.DataObject> classe. La <xref:System.Windows.DataObject> classe stock è sufficiente per molti scenari comuni di trasferimento dei dati.  
  
 Esistono diversi formati predefiniti, ad esempio bitmap, CSV, file, HTML, RTF, stringa, testo e audio. Per informazioni sui formati di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]dati predefiniti <xref:System.Windows.DataFormats> forniti con , vedere l'argomento di riferimento sulla classe .  
  
 Gli oggetti dati includono in genere una funzionalità per la conversione automatica dei dati archiviati in un formato in un formato diverso durante l'estrazione dei dati; questa funzione viene definita auto-conversione. Quando si esegue una query per i formati dati disponibili in un oggetto dati, i <xref:System.Windows.DataObject.GetFormats%28System.Boolean%29> <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> formati dati convertibili automaticamente possono essere filtrati dai formati dati nativi chiamando il metodo o e specificando il `autoConvert` parametro come `false`.  Quando si aggiungono dati a <xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%2CSystem.Boolean%29> un oggetto dati con il metodo , `autoConvert` è `false`possibile impedire la conversione automatica dei dati impostando il parametro su .  
  
<a name="Working_with_Data_Objects"></a>
## <a name="working-with-data-objects"></a>Utilizzo di oggetti datiWorking with Data Objects  
 In questa sezione vengono descritte le tecniche comuni per la creazione e l'utilizzo di oggetti dati.  
  
### <a name="creating-new-data-objects"></a>Creazione di nuovi oggetti datiCreating New Data Objects  
 La <xref:System.Windows.DataObject> classe fornisce diversi costruttori di overload che <xref:System.Windows.DataObject> facilitano il popolamento di una nuova istanza con una singola coppia di formato dati/dati.  
  
 Il codice di esempio seguente crea un nuovo oggetto <xref:System.Windows.DataObject.%23ctor%2A>dati<xref:System.Windows.DataObject.%23ctor(System.String,System.Object)>e utilizza uno dei costruttori di overload ( ) per inizializzare l'oggetto dati con una stringa e un formato dati specificato.  In questo caso, il formato dei dati è specificato da una stringa; la <xref:System.Windows.DataFormats> classe fornisce un set di stringhe di tipo predefinite. La conversione automatica dei dati memorizzati è consentita per impostazione predefinita.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring)]  
  
 Per ulteriori esempi di codice per la creazione di un oggetto dati, vedere [Creare un oggetto dati](how-to-create-a-data-object.md).  
  
### <a name="storing-data-in-multiple-formats"></a>Memorizzazione dei dati in più formati  
 Un singolo oggetto dati è in grado di archiviare i dati in più formati.   L'utilizzo strategico di più formati di dati all'interno di un singolo oggetto dati rende potenzialmente l'oggetto dati utilizzabile da una varietà più ampia di destinazioni di rilascio rispetto a quando è possibile rappresentare un solo formato dati.  Si noti che, in generale, un'origine di trascinamento deve essere indipendente sui formati di dati che possono essere utilizzati dalle potenziali destinazioni di rilascio.  
  
 Nell'esempio seguente viene <xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%29> illustrato come utilizzare il metodo per aggiungere dati a un oggetto dati in più formati.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_storemultipleformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_storemultipleformats)]  
  
### <a name="querying-a-data-object-for-available-formats"></a>Esecuzione di query su un oggetto dati per i formati disponibiliQuerying a Data Object for Available Formats  
 Poiché un singolo oggetto dati può contenere un numero arbitrario di formati di dati, gli oggetti dati includono funzionalità per il recupero di un elenco di formati dati disponibili.  
  
 Il codice di <xref:System.Windows.DataObject.GetFormats%2A> esempio seguente usa l'overload per ottenere una matrice di stringhe che indicano tutti i formati di dati disponibili in un oggetto dati (sia nativo che tramite conversione automatica).  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats)]  
  
 Per ulteriori esempi di codice che esegue una query su un oggetto dati per i formati dati disponibili, vedere [Elencare i formati dati in un oggetto dati](how-to-list-the-data-formats-in-a-data-object.md).  Per esempi di query su un oggetto dati per la presenza di un particolare formato dati, vedere [Determinare se un formato dati è presente in un oggetto dati.](how-to-determine-if-a-data-format-is-present-in-a-data-object.md)  
  
### <a name="retrieving-data-from-a-data-object"></a>Recupero di dati da un oggetto datiRetrieving Data from a Data Object  
 Il recupero di dati da un oggetto dati in <xref:System.Windows.DataObject.GetData%2A> un formato particolare implica semplicemente la chiamata a uno dei metodi e la specifica del formato dati desiderato.  Uno dei <xref:System.Windows.DataObject.GetDataPresent%2A> metodi può essere utilizzato per verificare la presenza di un particolare formato di dati.  <xref:System.Windows.DataObject.GetData%2A>restituisce i <xref:System.Object>dati in un oggetto ; a seconda del formato dei dati, è possibile eseguire il cast di questo oggetto in un contenitore specifico del tipo.  
  
 Il codice di <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> esempio seguente usa l'overload per verificare se un formato dati specificato è disponibile (nativo o tramite conversione automatica). Se il formato specificato è disponibile, nell'esempio <xref:System.Windows.DataObject.GetData%28System.String%29> vengono recuperati i dati utilizzando il metodo .  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat)]  
  
 Per ulteriori esempi di codice che recupera dati da un oggetto dati, vedere [Recupero di dati in un formato dati specifico](how-to-retrieve-data-in-a-particular-data-format.md).  
  
### <a name="removing-data-from-a-data-object"></a>Rimozione di dati da un oggetto datiRemoving Data From a Data Object  
 I dati non possono essere rimossi direttamente da un oggetto dati.  Per rimuovere in modo efficace i dati da un oggetto dati, attenersi alla seguente procedura:  
  
1. Creare un nuovo oggetto dati che conterrà solo i dati che si desidera conservare.  
  
2. "Copiare" i dati desiderati dall'oggetto dati precedente al nuovo oggetto dati.  Per copiare i dati, <xref:System.Windows.DataObject.GetData%2A> utilizzare uno <xref:System.Object> dei metodi per recuperare un che <xref:System.Windows.DataObject.SetData%2A> contiene i dati non elaborati e quindi utilizzare uno dei metodi per aggiungere i dati al nuovo oggetto dati.  
  
3. Sostituire l'oggetto dati precedente con quello nuovo.  
  
> [!NOTE]
> I <xref:System.Windows.DataObject.SetData%2A> metodi aggiungono solo dati a un oggetto dati. non sostituiscono i dati, anche se i dati e il formato dei dati sono esattamente gli stessi di una chiamata precedente. Se <xref:System.Windows.DataObject.SetData%2A> si chiama due volte per gli stessi dati e lo stesso formato dati, il formato dati/dati sarà presente due volte nell'oggetto dati.
