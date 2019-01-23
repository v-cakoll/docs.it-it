---
title: 'Procedura: Determinare se un formato di dati è presente in un oggetto dati'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataFormats class [WPF]
- drag-and-drop [WPF], data formats present
- data formats [WPF], determining if present
ms.assetid: e487a454-c9fc-4e53-aeaa-c458d059ad4c
ms.openlocfilehash: 603ecf8945e461f281a49b430de8342c41203463
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54546911"
---
# <a name="how-to-determine-if-a-data-format-is-present-in-a-data-object"></a><span data-ttu-id="b1376-102">Procedura: Determinare se un formato di dati è presente in un oggetto dati</span><span class="sxs-lookup"><span data-stu-id="b1376-102">How to: Determine if a Data Format is Present in a Data Object</span></span>
<span data-ttu-id="b1376-103">Gli esempi seguenti illustrano come usare i vari <xref:System.Windows.DataObject.GetDataPresent%2A> overload del metodo di query se un particolare formato dati è presente in un oggetto dati.</span><span class="sxs-lookup"><span data-stu-id="b1376-103">The following examples show how to use the various <xref:System.Windows.DataObject.GetDataPresent%2A> method overloads to query whether a particular data format is present in a data object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b1376-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="b1376-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="b1376-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b1376-105">Description</span></span>  
 <span data-ttu-id="b1376-106">Il codice di esempio seguente usa il <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> overload per eseguire query per la presenza di un formato dati particolare dalla stringa del descrittore.</span><span class="sxs-lookup"><span data-stu-id="b1376-106">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> overload to query for the presence of a particular data format by descriptor string.</span></span>  
  
### <a name="code"></a><span data-ttu-id="b1376-107">Codice</span><span class="sxs-lookup"><span data-stu-id="b1376-107">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_String](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_querydataformats_string)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_String](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_querydataformats_string)]  
  
## <a name="example"></a><span data-ttu-id="b1376-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="b1376-108">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="b1376-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b1376-109">Description</span></span>  
 <span data-ttu-id="b1376-110">Il codice di esempio seguente usa il <xref:System.Windows.DataObject.GetDataPresent%28System.Type%29> overload per eseguire query per la presenza di un formato di dati determinato dal tipo.</span><span class="sxs-lookup"><span data-stu-id="b1376-110">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.Type%29> overload to query for the presence of a particular data format by type.</span></span>  
  
### <a name="code"></a><span data-ttu-id="b1376-111">Codice</span><span class="sxs-lookup"><span data-stu-id="b1376-111">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Type](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_querydataformats_type)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Type](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_querydataformats_type)]  
  
## <a name="example"></a><span data-ttu-id="b1376-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="b1376-112">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="b1376-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b1376-113">Description</span></span>  
 <span data-ttu-id="b1376-114">Il codice di esempio seguente usa il <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> overload per eseguire query sui dati dalla stringa del descrittore e specifica come trattare i formati di dati di conversione automatica.</span><span class="sxs-lookup"><span data-stu-id="b1376-114">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> overload to query for data by descriptor string, and specifying how to treat auto-convertible data formats.</span></span>  
  
### <a name="code"></a><span data-ttu-id="b1376-115">Codice</span><span class="sxs-lookup"><span data-stu-id="b1376-115">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Autoconvert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_querydataformats_autoconvert)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Autoconvert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_querydataformats_autoconvert)]  
  
## <a name="see-also"></a><span data-ttu-id="b1376-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b1376-116">See also</span></span>
- <xref:System.Windows.IDataObject>
