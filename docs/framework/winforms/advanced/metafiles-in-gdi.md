---
title: Metafile in GDI+
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
- images [Windows Forms], metafiles
- GDI+, metafiles
- metafiles
ms.assetid: 51da872c-c783-440f-8bf6-1e580a966c31
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2b9d378f82b2a7edca00fedaacdcc0fca179c5a0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="metafiles-in-gdi"></a><span data-ttu-id="875c0-102">Metafile in GDI+</span><span class="sxs-lookup"><span data-stu-id="875c0-102">Metafiles in GDI+</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="875c0-103">fornisce la <xref:System.Drawing.Imaging.Metafile> classe in modo che è possibile registrare e visualizzare metafile.</span><span class="sxs-lookup"><span data-stu-id="875c0-103"> provides the <xref:System.Drawing.Imaging.Metafile> class so that you can record and display metafiles.</span></span> <span data-ttu-id="875c0-104">Un metafile, denominato anche immagine vettore, è un'immagine che viene archiviata come una sequenza di comandi e le impostazioni di disegno.</span><span class="sxs-lookup"><span data-stu-id="875c0-104">A metafile, also called a vector image, is an image that is stored as a sequence of drawing commands and settings.</span></span> <span data-ttu-id="875c0-105">I comandi e le impostazioni di registrazione un <xref:System.Drawing.Imaging.Metafile> oggetto può essere archiviato in memoria o salvato in un file o flusso.</span><span class="sxs-lookup"><span data-stu-id="875c0-105">The commands and settings recorded in a <xref:System.Drawing.Imaging.Metafile> object can be stored in memory or saved to a file or stream.</span></span>  
  
## <a name="metafile-formats"></a><span data-ttu-id="875c0-106">Formati Metafile</span><span class="sxs-lookup"><span data-stu-id="875c0-106">Metafile Formats</span></span>  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="875c0-107">è possibile visualizzare metafile che sono stati archiviati nei formati seguenti:</span><span class="sxs-lookup"><span data-stu-id="875c0-107"> can display metafiles that have been stored in the following formats:</span></span>  
  
-   <span data-ttu-id="875c0-108">Metafile di Windows (WMF)</span><span class="sxs-lookup"><span data-stu-id="875c0-108">Windows Metafile (WMF)</span></span>  
  
-   <span data-ttu-id="875c0-109">Enhanced Metafile (EMF)</span><span class="sxs-lookup"><span data-stu-id="875c0-109">Enhanced Metafile (EMF)</span></span>  
  
-   <span data-ttu-id="875c0-110">EMF +</span><span class="sxs-lookup"><span data-stu-id="875c0-110">EMF+</span></span>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="875c0-111">è possibile registrare metafile in formato EMF e EMF +, ma non nel formato WMF.</span><span class="sxs-lookup"><span data-stu-id="875c0-111"> can record metafiles in the EMF and EMF+ formats, but not in the WMF format.</span></span>  
  
 <span data-ttu-id="875c0-112">EMF + è un'estensione di EMF che consente [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] record da archiviare.</span><span class="sxs-lookup"><span data-stu-id="875c0-112">EMF+ is an extension to EMF that allows [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] records to be stored.</span></span> <span data-ttu-id="875c0-113">Esistono due varianti nel formato EMF +: EMF + solo ed EMF + Dual.</span><span class="sxs-lookup"><span data-stu-id="875c0-113">There are two variations on the EMF+ format: EMF+ Only and EMF+ Dual.</span></span> <span data-ttu-id="875c0-114">Metafile EMF + solo contengono solo [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] record.</span><span class="sxs-lookup"><span data-stu-id="875c0-114">EMF+ Only metafiles contain only [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] records.</span></span> <span data-ttu-id="875c0-115">È possibile visualizzare tali metafile da [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] ma non dal [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].</span><span class="sxs-lookup"><span data-stu-id="875c0-115">Such metafiles can be displayed by [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] but not by [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].</span></span> <span data-ttu-id="875c0-116">Metafile EMF + contengono [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] e [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] record.</span><span class="sxs-lookup"><span data-stu-id="875c0-116">EMF+ Dual metafiles contain [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] and [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] records.</span></span> <span data-ttu-id="875c0-117">Ogni [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] record in un formato EMF + Dual metafile è associato a un'alternativa [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] record.</span><span class="sxs-lookup"><span data-stu-id="875c0-117">Each [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] record in an EMF+ Dual metafile is paired with an alternate [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] record.</span></span> <span data-ttu-id="875c0-118">È possibile visualizzare tali metafile da [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] o [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].</span><span class="sxs-lookup"><span data-stu-id="875c0-118">Such metafiles can be displayed by [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] or by [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].</span></span>  
  
 <span data-ttu-id="875c0-119">L'esempio seguente mostra un metafile precedentemente salvato come file.</span><span class="sxs-lookup"><span data-stu-id="875c0-119">The following example displays a metafile that was previously saved as a file.</span></span> <span data-ttu-id="875c0-120">Metafile viene visualizzato con il relativo angolo superiore sinistro a (100, 100).</span><span class="sxs-lookup"><span data-stu-id="875c0-120">The metafile is displayed with its upper-left corner at (100, 100).</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="875c0-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="875c0-121">See Also</span></span>  
 [<span data-ttu-id="875c0-122">Immagini, bitmap e metafile</span><span class="sxs-lookup"><span data-stu-id="875c0-122">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)
