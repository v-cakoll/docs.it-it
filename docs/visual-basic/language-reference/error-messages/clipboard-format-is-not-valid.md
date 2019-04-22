---
title: Formato degli Appunti non valido
ms.date: 07/20/2015
f1_keywords:
- vbrID460
ms.assetid: 71a4a045-65bb-417d-b3bd-99a9fa3c53f6
ms.openlocfilehash: 5ec077be30b0afc8917d431dc9bd73c8dd41be89
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58817178"
---
# <a name="clipboard-format-is-not-valid"></a><span data-ttu-id="e9375-102">Formato degli Appunti non valido</span><span class="sxs-lookup"><span data-stu-id="e9375-102">Clipboard format is not valid</span></span>
<span data-ttu-id="e9375-103">Il formato degli Appunti specificato non è compatibile con il metodo in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e9375-103">The specified Clipboard format is incompatible with the method being executed.</span></span> <span data-ttu-id="e9375-104">Tra le possibili cause di questo errore sono:</span><span class="sxs-lookup"><span data-stu-id="e9375-104">Among the possible causes for this error are:</span></span>  
  
-   <span data-ttu-id="e9375-105">Usando gli Appunti `GetText` oppure `SetText` metodo con un formato degli Appunti diverso da `vbCFText` o `vbCFLink`.</span><span class="sxs-lookup"><span data-stu-id="e9375-105">Using the Clipboard's `GetText` or `SetText` method with a Clipboard format other than `vbCFText` or `vbCFLink`.</span></span>  
  
-   <span data-ttu-id="e9375-106">Usando gli Appunti `GetData` oppure `SetData` metodo con un formato degli Appunti diverso da `vbCFBitmap`, `vbCFDIB`, o `vbCFMetafile`.</span><span class="sxs-lookup"><span data-stu-id="e9375-106">Using the Clipboard's `GetData` or `SetData` method with a Clipboard format other than `vbCFBitmap`, `vbCFDIB`, or `vbCFMetafile`.</span></span>  
  
-   <span data-ttu-id="e9375-107">Usando il `GetData` oppure `SetData` metodi di un `DataObject` con un formato degli Appunti nell'intervallo riservato da Microsoft Windows per registrati formati (HC000- & HFFFF), quando il formato degli Appunti non è stato registrato con Microsoft Windows .</span><span class="sxs-lookup"><span data-stu-id="e9375-107">Using the `GetData` or `SetData` methods of a `DataObject` with a Clipboard format in the range reserved by Microsoft Windows for registered formats (&HC000-&HFFFF), when that Clipboard format has not been registered with Microsoft Windows.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e9375-108">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="e9375-108">To correct this error</span></span>  
  
-   <span data-ttu-id="e9375-109">Rimuovere il formato non valido e specificarne uno valido.</span><span class="sxs-lookup"><span data-stu-id="e9375-109">Remove the invalid format and specify a valid one.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9375-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9375-110">See also</span></span>

- [<span data-ttu-id="e9375-111">Appunti: Aggiunta di altri formati</span><span class="sxs-lookup"><span data-stu-id="e9375-111">Clipboard: Adding Other Formats</span></span>](/cpp/mfc/clipboard-adding-other-formats)
