---
title: 'Procedura: recuperare dati in un formato dati particolare'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drag-and-drop [WPF], retrieving data
- DataFormats class [WPF], retrieving data
- DataObject class [WPF], retrieving data
ms.assetid: a625acf3-1144-44cd-add7-456aefc3859f
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8e6513fd6d8d443b76059626c0e40991e35830c6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-retrieve-data-in-a-particular-data-format"></a><span data-ttu-id="9f279-102">Procedura: recuperare dati in un formato dati particolare</span><span class="sxs-lookup"><span data-stu-id="9f279-102">How to: Retrieve Data in a Particular Data Format</span></span>
<span data-ttu-id="9f279-103">Nell'esempio seguente viene illustrato come recuperare i dati da un oggetto dati in un formato specificato.</span><span class="sxs-lookup"><span data-stu-id="9f279-103">The following examples show how to retrieve data from a data object in a specified format.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9f279-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="9f279-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="9f279-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9f279-105">Description</span></span>  
 <span data-ttu-id="9f279-106">Il codice di esempio seguente usa il <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> eseguire l'overload per controllare innanzitutto se formattare una data specificata è disponibile (in modo nativo o tramite conversione automatica); se il formato specificato non è disponibile, l'esempio recupera i dati utilizzando il <xref:System.Windows.DataObject.GetData%28System.String%29> metodo.</span><span class="sxs-lookup"><span data-stu-id="9f279-106">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> overload to first check if a specified data format is available (natively or by auto-convert); if the specified format is available, the example retrieves the data by using the <xref:System.Windows.DataObject.GetData%28System.String%29> method.</span></span>  
  
### <a name="code"></a><span data-ttu-id="9f279-107">Codice</span><span class="sxs-lookup"><span data-stu-id="9f279-107">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat)]  
  
## <a name="example"></a><span data-ttu-id="9f279-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="9f279-108">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="9f279-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9f279-109">Description</span></span>  
 <span data-ttu-id="9f279-110">Il codice di esempio seguente usa il <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> overload per verificare se un formato dati specificato è disponibile in modo nativo (formati di dati convertibili automaticamente sono filtrati); se il formato specificato non è disponibile, l'esempio recupera i dati utilizzando il <xref:System.Windows.DataObject.GetData%28System.String%29>metodo.</span><span class="sxs-lookup"><span data-stu-id="9f279-110">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> overload to first check if a specified data format is available natively (auto-convertible data formats are filtered); if the specified format is available, the example retrieves the data by using the <xref:System.Windows.DataObject.GetData%28System.String%29> method.</span></span>  
  
### <a name="code"></a><span data-ttu-id="9f279-111">Codice</span><span class="sxs-lookup"><span data-stu-id="9f279-111">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat_Native](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat_native)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat_Native](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat_native)]  
  
## <a name="see-also"></a><span data-ttu-id="9f279-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9f279-112">See Also</span></span>  
 <xref:System.Windows.IDataObject>  
 [<span data-ttu-id="9f279-113">Cenni preliminari sul trascinamento della selezione</span><span class="sxs-lookup"><span data-stu-id="9f279-113">Drag and Drop Overview</span></span>](../../../../docs/framework/wpf/advanced/drag-and-drop-overview.md)
