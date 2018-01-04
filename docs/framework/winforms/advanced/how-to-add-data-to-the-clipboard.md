---
title: 'Procedura: aggiungere dati agli Appunti'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Clipboard [Windows Forms], copying data to
- data [Windows Forms], copying to Clipboard
ms.assetid: 25152454-0e78-40a9-8a9e-a2a5a274e517
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 452dfc5a9645e8f43ab583099deec60faa2d1b4d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-data-to-the-clipboard"></a><span data-ttu-id="9c113-102">Procedura: aggiungere dati agli Appunti</span><span class="sxs-lookup"><span data-stu-id="9c113-102">How to: Add Data to the Clipboard</span></span>
<span data-ttu-id="9c113-103">La <xref:System.Windows.Forms.Clipboard> classe fornisce metodi che è possibile utilizzare per interagire con la funzionalità degli Appunti di sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="9c113-103">The <xref:System.Windows.Forms.Clipboard> class provides methods that you can use to interact with the Windows operating system Clipboard feature.</span></span> <span data-ttu-id="9c113-104">Molte applicazioni utilizzano negli Appunti come archivio temporaneo per i dati.</span><span class="sxs-lookup"><span data-stu-id="9c113-104">Many applications use the Clipboard as a temporary repository for data.</span></span> <span data-ttu-id="9c113-105">Elaboratori di testo, ad esempio, usare gli Appunti durante le operazioni di taglia e Incolla.</span><span class="sxs-lookup"><span data-stu-id="9c113-105">For example, word processors use the Clipboard during cut-and-paste operations.</span></span> <span data-ttu-id="9c113-106">Sono utili per il trasferimento di dati da un'applicazione a altra anche negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="9c113-106">The Clipboard is also useful for transferring data from one application to another.</span></span>  
  
 <span data-ttu-id="9c113-107">Quando si aggiungono dati negli Appunti, è possibile indicare il formato dei dati in modo che le altre applicazioni possono riconoscere i dati se è possibile utilizzare tale formato.</span><span class="sxs-lookup"><span data-stu-id="9c113-107">When you add data to the Clipboard, you can indicate the data format so that other applications can recognize the data if they can use that format.</span></span> <span data-ttu-id="9c113-108">È anche possibile aggiungere dati negli Appunti in più formati diversi per aumentare il numero di altre applicazioni che possono utilizzare i dati.</span><span class="sxs-lookup"><span data-stu-id="9c113-108">You can also add data to the Clipboard in multiple different formats to increase the number of other applications that can potentially use the data.</span></span>  
  
 <span data-ttu-id="9c113-109">Un formato degli Appunti è una stringa che identifica il formato in modo che un'applicazione che utilizza tale formato può recuperare i dati associati.</span><span class="sxs-lookup"><span data-stu-id="9c113-109">A Clipboard format is a string that identifies the format so that an application that uses that format can retrieve the associated data.</span></span> <span data-ttu-id="9c113-110">La <xref:System.Windows.Forms.DataFormats> classe fornisce i nomi di formato predefinito per l'uso.</span><span class="sxs-lookup"><span data-stu-id="9c113-110">The <xref:System.Windows.Forms.DataFormats> class provides predefined format names for your use.</span></span> <span data-ttu-id="9c113-111">È inoltre possibile utilizzare nomi di formato personalizzati o utilizzare il tipo di oggetto come formato.</span><span class="sxs-lookup"><span data-stu-id="9c113-111">You can also use your own format names or use the type of an object as its format.</span></span>  
  
 <span data-ttu-id="9c113-112">Per aggiungere i dati negli Appunti in uno o più formati, utilizzare il <xref:System.Windows.Forms.Clipboard.SetDataObject%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="9c113-112">To add data to the Clipboard in one or multiple formats, use the <xref:System.Windows.Forms.Clipboard.SetDataObject%2A> method.</span></span> <span data-ttu-id="9c113-113">È possibile passare qualsiasi oggetto a questo metodo, ma per aggiungere dati in più formati, è innanzitutto necessario aggiungere i dati per un oggetto separato, progettato per funzionare con più formati.</span><span class="sxs-lookup"><span data-stu-id="9c113-113">You can pass any object to this method, but to add data in multiple formats, you must first add the data to a separate object designed to work with multiple formats.</span></span> <span data-ttu-id="9c113-114">In genere, si aggiungerà i dati in un <xref:System.Windows.Forms.DataObject>, ma è possibile utilizzare qualsiasi tipo che implementa il <xref:System.Windows.Forms.IDataObject> interfaccia.</span><span class="sxs-lookup"><span data-stu-id="9c113-114">Typically, you will add your data to a <xref:System.Windows.Forms.DataObject>, but you can use any type that implements the <xref:System.Windows.Forms.IDataObject> interface.</span></span>  
  
 <span data-ttu-id="9c113-115">In [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)], è possibile aggiungere dati direttamente negli Appunti utilizzando nuovi metodi progettati per semplificare le attività di base negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="9c113-115">In [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)], you can add data directly to the Clipboard by using new methods designed to make basic Clipboard tasks easier.</span></span> <span data-ttu-id="9c113-116">Utilizzare questi metodi quando si lavora con dati in un formato comune, ad esempio testo.</span><span class="sxs-lookup"><span data-stu-id="9c113-116">Use these methods when you work with data in a single, common format such as text.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9c113-117">Tutte le applicazioni basate su Windows condividono negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="9c113-117">All Windows-based applications share the Clipboard.</span></span> <span data-ttu-id="9c113-118">Pertanto, il contenuto è soggetto a modifiche quando si passa a un'altra applicazione.</span><span class="sxs-lookup"><span data-stu-id="9c113-118">Therefore, the contents are subject to change when you switch to another application.</span></span>  
>   
>  <span data-ttu-id="9c113-119">La <xref:System.Windows.Forms.Clipboard> classe può essere utilizzata solo nei thread impostati sulla modalità single thread apartment (STA).</span><span class="sxs-lookup"><span data-stu-id="9c113-119">The <xref:System.Windows.Forms.Clipboard> class can only be used in threads set to single thread apartment (STA) mode.</span></span> <span data-ttu-id="9c113-120">Per utilizzare questa classe, assicurarsi che il `Main` metodo è contrassegnato con il <xref:System.STAThreadAttribute> attributo.</span><span class="sxs-lookup"><span data-stu-id="9c113-120">To use this class, ensure that your `Main` method is marked with the <xref:System.STAThreadAttribute> attribute.</span></span>  
>   
>  <span data-ttu-id="9c113-121">Un oggetto deve essere serializzabile per poter essere inserito negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="9c113-121">An object must be serializable for it to be put on the Clipboard.</span></span> <span data-ttu-id="9c113-122">Per rendere un tipo serializzabile, contrassegnarlo con il <xref:System.SerializableAttribute> attributo.</span><span class="sxs-lookup"><span data-stu-id="9c113-122">To make a type serializable, mark it with the <xref:System.SerializableAttribute> attribute.</span></span> <span data-ttu-id="9c113-123">Se si passa un oggetto non serializzabile a un metodo negli Appunti, il metodo avrà esito negativo senza generare un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="9c113-123">If you pass a non-serializable object to a Clipboard method, the method will fail without throwing an exception.</span></span> <span data-ttu-id="9c113-124">Per altre informazioni sulla serializzazione, vedere <xref:System.Runtime.Serialization>.</span><span class="sxs-lookup"><span data-stu-id="9c113-124">For more information about serialization, see <xref:System.Runtime.Serialization>.</span></span>  
  
### <a name="to-add-data-to-the-clipboard-in-a-single-common-format"></a><span data-ttu-id="9c113-125">Per aggiungere i dati negli Appunti in un formato comune</span><span class="sxs-lookup"><span data-stu-id="9c113-125">To add data to the Clipboard in a single, common format</span></span>  
  
1.  <span data-ttu-id="9c113-126">Utilizzare il <xref:System.Windows.Forms.Clipboard.SetAudio%2A>, <xref:System.Windows.Forms.Clipboard.SetFileDropList%2A>, <xref:System.Windows.Forms.Clipboard.SetImage%2A>, o <xref:System.Windows.Forms.Clipboard.SetText%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="9c113-126">Use the <xref:System.Windows.Forms.Clipboard.SetAudio%2A>, <xref:System.Windows.Forms.Clipboard.SetFileDropList%2A>, <xref:System.Windows.Forms.Clipboard.SetImage%2A>, or <xref:System.Windows.Forms.Clipboard.SetText%2A> method.</span></span> <span data-ttu-id="9c113-127">Questi metodi sono disponibili solo in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9c113-127">These methods are available only in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span></span>  
  
     [!code-csharp[System.Windows.Forms.Clipboard#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.Clipboard#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#2)]  
  
### <a name="to-add-data-to-the-clipboard-in-a-custom-format"></a><span data-ttu-id="9c113-128">Per aggiungere i dati negli Appunti in un formato personalizzato</span><span class="sxs-lookup"><span data-stu-id="9c113-128">To add data to the Clipboard in a custom format</span></span>  
  
1.  <span data-ttu-id="9c113-129">Utilizzare il <xref:System.Windows.Forms.Clipboard.SetData%2A> metodo con un nome di formato personalizzata.</span><span class="sxs-lookup"><span data-stu-id="9c113-129">Use the <xref:System.Windows.Forms.Clipboard.SetData%2A> method with a custom format name.</span></span> <span data-ttu-id="9c113-130">Questo metodo è disponibile solo in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9c113-130">This method is available only in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span></span>  
  
     <span data-ttu-id="9c113-131">È inoltre possibile utilizzare nomi di formato predefiniti con il <xref:System.Windows.Forms.Clipboard.SetData%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="9c113-131">You can also use predefined format names with the <xref:System.Windows.Forms.Clipboard.SetData%2A> method.</span></span> <span data-ttu-id="9c113-132">Per altre informazioni, vedere <xref:System.Windows.Forms.DataFormats>.</span><span class="sxs-lookup"><span data-stu-id="9c113-132">For more information, see <xref:System.Windows.Forms.DataFormats>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Clipboard#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.Clipboard#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#3)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
### <a name="to-add-data-to-the-clipboard-in-multiple-formats"></a><span data-ttu-id="9c113-133">Per aggiungere i dati negli Appunti in più formati</span><span class="sxs-lookup"><span data-stu-id="9c113-133">To add data to the Clipboard in multiple formats</span></span>  
  
1.  <span data-ttu-id="9c113-134">Utilizzare il <xref:System.Windows.Forms.Clipboard.SetDataObject%2A> (metodo) e passare un <xref:System.Windows.Forms.DataObject> che contiene i dati.</span><span class="sxs-lookup"><span data-stu-id="9c113-134">Use the <xref:System.Windows.Forms.Clipboard.SetDataObject%2A> method and pass in a <xref:System.Windows.Forms.DataObject> that contains your data.</span></span> <span data-ttu-id="9c113-135">È necessario utilizzare questo metodo per aggiungere dati agli Appunti nelle versioni precedenti a [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9c113-135">You must use this method to add data to the Clipboard on versions earlier than [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)].</span></span>  
  
     [!code-csharp[System.Windows.Forms.Clipboard#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.Clipboard#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#4)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
## <a name="see-also"></a><span data-ttu-id="9c113-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9c113-136">See Also</span></span>  
 <span data-ttu-id="9c113-137">[Drag-and-Drop Operations and Clipboard Support](../../../../docs/framework/winforms/advanced/drag-and-drop-operations-and-clipboard-support.md) (Supporto delle operazioni di trascinamento della selezione e degli Appunti)</span><span class="sxs-lookup"><span data-stu-id="9c113-137">[Drag-and-Drop Operations and Clipboard Support](../../../../docs/framework/winforms/advanced/drag-and-drop-operations-and-clipboard-support.md)</span></span>  
 [<span data-ttu-id="9c113-138">Procedura: Recuperare dati dagli Appunti</span><span class="sxs-lookup"><span data-stu-id="9c113-138">How to: Retrieve Data from the Clipboard</span></span>](../../../../docs/framework/winforms/advanced/how-to-retrieve-data-from-the-clipboard.md)
