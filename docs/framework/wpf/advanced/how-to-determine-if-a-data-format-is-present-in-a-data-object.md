---
title: "Procedura: determinare se un formato di dati è presente in un oggetto dati"
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
- DataFormats class [WPF]
- drag-and-drop [WPF], data formats present
- data formats [WPF], determining if present
ms.assetid: e487a454-c9fc-4e53-aeaa-c458d059ad4c
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9e5eaad64e18ff955340a8e91bfe8bd0e09dd8d7
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-determine-if-a-data-format-is-present-in-a-data-object"></a><span data-ttu-id="9bb71-102">Procedura: determinare se un formato di dati è presente in un oggetto dati</span><span class="sxs-lookup"><span data-stu-id="9bb71-102">How to: Determine if a Data Format is Present in a Data Object</span></span>
<span data-ttu-id="9bb71-103">Nell'esempio seguente viene illustrato come utilizzare i vari <xref:System.Windows.DataObject.GetDataPresent%2A> overload del metodo di query se un particolare formato dati è presente in un oggetto dati.</span><span class="sxs-lookup"><span data-stu-id="9bb71-103">The following examples show how to use the various <xref:System.Windows.DataObject.GetDataPresent%2A> method overloads to query whether a particular data format is present in a data object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9bb71-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="9bb71-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="9bb71-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9bb71-105">Description</span></span>  
 <span data-ttu-id="9bb71-106">Il codice di esempio seguente usa il <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> overload per eseguire query per la presenza di un particolare formato dati da una stringa del descrittore.</span><span class="sxs-lookup"><span data-stu-id="9bb71-106">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> overload to query for the presence of a particular data format by descriptor string.</span></span>  
  
### <a name="code"></a><span data-ttu-id="9bb71-107">Codice</span><span class="sxs-lookup"><span data-stu-id="9bb71-107">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_String](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_querydataformats_string)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_String](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_querydataformats_string)]  
  
## <a name="example"></a><span data-ttu-id="9bb71-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="9bb71-108">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="9bb71-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9bb71-109">Description</span></span>  
 <span data-ttu-id="9bb71-110">Il codice di esempio seguente usa il <xref:System.Windows.DataObject.GetDataPresent%28System.Type%29> overload per eseguire query per la presenza di un particolare formato dati dal tipo.</span><span class="sxs-lookup"><span data-stu-id="9bb71-110">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.Type%29> overload to query for the presence of a particular data format by type.</span></span>  
  
### <a name="code"></a><span data-ttu-id="9bb71-111">Codice</span><span class="sxs-lookup"><span data-stu-id="9bb71-111">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Type](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_querydataformats_type)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Type](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_querydataformats_type)]  
  
## <a name="example"></a><span data-ttu-id="9bb71-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="9bb71-112">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="9bb71-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9bb71-113">Description</span></span>  
 <span data-ttu-id="9bb71-114">Il codice di esempio seguente usa il <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> overload per eseguire query sui dati da una stringa del descrittore e specificando la modalità di gestione di formati di dati convertibili automaticamente.</span><span class="sxs-lookup"><span data-stu-id="9bb71-114">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> overload to query for data by descriptor string, and specifying how to treat auto-convertible data formats.</span></span>  
  
### <a name="code"></a><span data-ttu-id="9bb71-115">Codice</span><span class="sxs-lookup"><span data-stu-id="9bb71-115">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Autoconvert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_querydataformats_autoconvert)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Autoconvert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_querydataformats_autoconvert)]  
  
## <a name="see-also"></a><span data-ttu-id="9bb71-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9bb71-116">See Also</span></span>  
 <xref:System.Windows.IDataObject>
