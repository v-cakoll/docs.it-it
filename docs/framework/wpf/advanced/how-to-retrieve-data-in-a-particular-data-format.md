---
title: 'Procedura: Recuperare dati in un formato dati particolare'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drag-and-drop [WPF], retrieving data
- DataFormats class [WPF], retrieving data
- DataObject class [WPF], retrieving data
ms.assetid: a625acf3-1144-44cd-add7-456aefc3859f
ms.openlocfilehash: b3ec1b8fa873fd449956912e9e77e98b0362cb0e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59080020"
---
# <a name="how-to-retrieve-data-in-a-particular-data-format"></a><span data-ttu-id="bb253-102">Procedura: Recuperare dati in un formato dati particolare</span><span class="sxs-lookup"><span data-stu-id="bb253-102">How to: Retrieve Data in a Particular Data Format</span></span>
<span data-ttu-id="bb253-103">Negli esempi seguenti mostrano come recuperare i dati da un oggetto dati in un formato specificato.</span><span class="sxs-lookup"><span data-stu-id="bb253-103">The following examples show how to retrieve data from a data object in a specified format.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bb253-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="bb253-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="bb253-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bb253-105">Description</span></span>  
 <span data-ttu-id="bb253-106">Il codice di esempio seguente usa il <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> overload per prima cosa controllare se i dati specificati di formato è disponibile (in modo nativo o tramite conversione automatica); se il formato specificato è disponibile, l'esempio recupera i dati utilizzando il <xref:System.Windows.DataObject.GetData%28System.String%29> (metodo).</span><span class="sxs-lookup"><span data-stu-id="bb253-106">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> overload to first check if a specified data format is available (natively or by auto-convert); if the specified format is available, the example retrieves the data by using the <xref:System.Windows.DataObject.GetData%28System.String%29> method.</span></span>  
  
### <a name="code"></a><span data-ttu-id="bb253-107">Codice</span><span class="sxs-lookup"><span data-stu-id="bb253-107">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat)]  
  
## <a name="example"></a><span data-ttu-id="bb253-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="bb253-108">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="bb253-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bb253-109">Description</span></span>  
 <span data-ttu-id="bb253-110">Il codice di esempio seguente usa il <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> overload prima di tutto verificare se un formato dati specificato è disponibile in modo nativo (formati convertibili automaticamente i dati vengono filtrati); se il formato specificato è disponibile, l'esempio recupera i dati usando il <xref:System.Windows.DataObject.GetData%28System.String%29>metodo.</span><span class="sxs-lookup"><span data-stu-id="bb253-110">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> overload to first check if a specified data format is available natively (auto-convertible data formats are filtered); if the specified format is available, the example retrieves the data by using the <xref:System.Windows.DataObject.GetData%28System.String%29> method.</span></span>  
  
### <a name="code"></a><span data-ttu-id="bb253-111">Codice</span><span class="sxs-lookup"><span data-stu-id="bb253-111">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat_Native](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat_native)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat_Native](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat_native)]  
  
## <a name="see-also"></a><span data-ttu-id="bb253-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bb253-112">See also</span></span>

- <xref:System.Windows.IDataObject>
- [<span data-ttu-id="bb253-113">Cenni preliminari sul trascinamento della selezione</span><span class="sxs-lookup"><span data-stu-id="bb253-113">Drag and Drop Overview</span></span>](drag-and-drop-overview.md)
