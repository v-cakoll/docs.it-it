---
title: Metafile in GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], metafiles
- GDI+, metafiles
- metafiles
ms.assetid: 51da872c-c783-440f-8bf6-1e580a966c31
ms.openlocfilehash: df54289722cf12bad840722c6eafdaa43279a5dc
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2019
ms.locfileid: "67504580"
---
# <a name="metafiles-in-gdi"></a><span data-ttu-id="df060-102">Metafile in GDI+</span><span class="sxs-lookup"><span data-stu-id="df060-102">Metafiles in GDI+</span></span>
<span data-ttu-id="df060-103">GDI+ è disponibile il <xref:System.Drawing.Imaging.Metafile> classe in modo che è possibile registrare e visualizzare metafile.</span><span class="sxs-lookup"><span data-stu-id="df060-103">GDI+ provides the <xref:System.Drawing.Imaging.Metafile> class so that you can record and display metafiles.</span></span> <span data-ttu-id="df060-104">Un metafile, denominato anche immagine vettoriale, è un'immagine che viene archiviata come una sequenza di comandi e le impostazioni di disegno.</span><span class="sxs-lookup"><span data-stu-id="df060-104">A metafile, also called a vector image, is an image that is stored as a sequence of drawing commands and settings.</span></span> <span data-ttu-id="df060-105">I comandi e le impostazioni registrate un <xref:System.Drawing.Imaging.Metafile> oggetto può essere archiviato in memoria o salvato in un file o flusso.</span><span class="sxs-lookup"><span data-stu-id="df060-105">The commands and settings recorded in a <xref:System.Drawing.Imaging.Metafile> object can be stored in memory or saved to a file or stream.</span></span>  
  
## <a name="metafile-formats"></a><span data-ttu-id="df060-106">Formati di metafile</span><span class="sxs-lookup"><span data-stu-id="df060-106">Metafile Formats</span></span>  
 <span data-ttu-id="df060-107">GDI+ possono visualizzare metafile che sono stati archiviati nei formati seguenti:</span><span class="sxs-lookup"><span data-stu-id="df060-107">GDI+ can display metafiles that have been stored in the following formats:</span></span>  
  
- <span data-ttu-id="df060-108">Windows Metafile (WMF)</span><span class="sxs-lookup"><span data-stu-id="df060-108">Windows Metafile (WMF)</span></span>  
  
- <span data-ttu-id="df060-109">Enhanced Metafile (EMF)</span><span class="sxs-lookup"><span data-stu-id="df060-109">Enhanced Metafile (EMF)</span></span>  
  
- <span data-ttu-id="df060-110">EMF+</span><span class="sxs-lookup"><span data-stu-id="df060-110">EMF+</span></span>  
  
 <span data-ttu-id="df060-111">GDI+ in grado di registrare i metafile in formato EMF e EMF +, ma non nel formato di WMF.</span><span class="sxs-lookup"><span data-stu-id="df060-111">GDI+ can record metafiles in the EMF and EMF+ formats, but not in the WMF format.</span></span>  
  
 <span data-ttu-id="df060-112">EMF + è un'estensione EMF che consente i record GDI+ da archiviare.</span><span class="sxs-lookup"><span data-stu-id="df060-112">EMF+ is an extension to EMF that allows GDI+ records to be stored.</span></span> <span data-ttu-id="df060-113">Esistono due varianti nel formato EMF +: EMF + solo ed EMF + Dual.</span><span class="sxs-lookup"><span data-stu-id="df060-113">There are two variations on the EMF+ format: EMF+ Only and EMF+ Dual.</span></span> <span data-ttu-id="df060-114">Metafile EMF + solo contengono solo record GDI+.</span><span class="sxs-lookup"><span data-stu-id="df060-114">EMF+ Only metafiles contain only GDI+ records.</span></span> <span data-ttu-id="df060-115">Tali metafile visualizzabili mediante GDI+, ma non GDI.</span><span class="sxs-lookup"><span data-stu-id="df060-115">Such metafiles can be displayed by GDI+ but not by GDI.</span></span> <span data-ttu-id="df060-116">Metafile EMF + Dual contengono record GDI+ e GDI.</span><span class="sxs-lookup"><span data-stu-id="df060-116">EMF+ Dual metafiles contain GDI+ and GDI records.</span></span> <span data-ttu-id="df060-117">Ogni record GDI+ in un metafile EMF + Dual viene abbinato a un record GDI alternativo.</span><span class="sxs-lookup"><span data-stu-id="df060-117">Each GDI+ record in an EMF+ Dual metafile is paired with an alternate GDI record.</span></span> <span data-ttu-id="df060-118">Tali metafile possono essere visualizzati mediante GDI+ o GDI.</span><span class="sxs-lookup"><span data-stu-id="df060-118">Such metafiles can be displayed by GDI+ or by GDI.</span></span>  
  
 <span data-ttu-id="df060-119">L'esempio seguente mostra un metafile salvato in precedenza come file.</span><span class="sxs-lookup"><span data-stu-id="df060-119">The following example displays a metafile that was previously saved as a file.</span></span> <span data-ttu-id="df060-120">Viene visualizzato il metafile con relativo angolo superiore sinistro a (100, 100).</span><span class="sxs-lookup"><span data-stu-id="df060-120">The metafile is displayed with its upper-left corner at (100, 100).</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="df060-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="df060-121">See also</span></span>

- [<span data-ttu-id="df060-122">Immagini, bitmap e metafile</span><span class="sxs-lookup"><span data-stu-id="df060-122">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
