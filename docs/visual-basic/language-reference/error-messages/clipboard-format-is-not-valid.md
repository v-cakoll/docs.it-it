---
title: Formato degli Appunti non valido
ms.date: 07/20/2015
f1_keywords:
- vbrID460
ms.assetid: 71a4a045-65bb-417d-b3bd-99a9fa3c53f6
ms.openlocfilehash: eef16096b269902dbaca6a344abf4c5f6a504fb7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33586221"
---
# <a name="clipboard-format-is-not-valid"></a><span data-ttu-id="c7b81-102">Formato degli Appunti non valido</span><span class="sxs-lookup"><span data-stu-id="c7b81-102">Clipboard format is not valid</span></span>
<span data-ttu-id="c7b81-103">Il formato degli Appunti specificato non è compatibile con il metodo in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="c7b81-103">The specified Clipboard format is incompatible with the method being executed.</span></span> <span data-ttu-id="c7b81-104">Le cause possibili di questo errore sono:</span><span class="sxs-lookup"><span data-stu-id="c7b81-104">Among the possible causes for this error are:</span></span>  
  
-   <span data-ttu-id="c7b81-105">Utilizzando gli Appunti `GetText` o `SetText` metodo con un formato degli Appunti diverso da `vbCFText` o `vbCFLink`.</span><span class="sxs-lookup"><span data-stu-id="c7b81-105">Using the Clipboard's `GetText` or `SetText` method with a Clipboard format other than `vbCFText` or `vbCFLink`.</span></span>  
  
-   <span data-ttu-id="c7b81-106">Utilizzando gli Appunti `GetData` o `SetData` metodo con un formato degli Appunti diverso da `vbCFBitmap`, `vbCFDIB`, o `vbCFMetafile`.</span><span class="sxs-lookup"><span data-stu-id="c7b81-106">Using the Clipboard's `GetData` or `SetData` method with a Clipboard format other than `vbCFBitmap`, `vbCFDIB`, or `vbCFMetafile`.</span></span>  
  
-   <span data-ttu-id="c7b81-107">Utilizzo di `DataObject``GetData` metodo o `SetData` metodo con un formato degli Appunti nell'intervallo riservato da Microsoft Windows ai formati registrati (& HC000 - & HFFFF), quando il formato degli Appunti non è stato registrato con Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="c7b81-107">Using the `DataObject``GetData` method or `SetData` method with a Clipboard format in the range reserved by Microsoft Windows for registered formats (&HC000-&HFFFF), when that Clipboard format has not been registered with Microsoft Windows.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c7b81-108">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="c7b81-108">To correct this error</span></span>  
  
-   <span data-ttu-id="c7b81-109">Rimuovere il formato non valido e specificarne uno valido.</span><span class="sxs-lookup"><span data-stu-id="c7b81-109">Remove the invalid format and specify a valid one.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7b81-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c7b81-110">See Also</span></span>  
 [<span data-ttu-id="c7b81-111">Appunti: aggiunta di altri formati</span><span class="sxs-lookup"><span data-stu-id="c7b81-111">Clipboard: Adding Other Formats</span></span>](/cpp/mfc/clipboard-adding-other-formats)
