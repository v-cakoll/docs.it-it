---
title: Errore di caricamento della DLL
ms.date: 07/20/2015
f1_keywords:
- vbrID48
ms.assetid: 4226cd1f-028c-477d-88a5-cb57f7e0cdc8
ms.openlocfilehash: fd2e425f2dd3f4127cd777d4a1f7ab9809de9d45
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409627"
---
# <a name="error-in-loading-dll-visual-basic"></a><span data-ttu-id="8e58a-102">Errore di caricamento della DLL (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8e58a-102">Error in loading DLL (Visual Basic)</span></span>
<span data-ttu-id="8e58a-103">Una libreria di collegamento dinamico (DLL) è una libreria specificata nella `Lib` clausola di un' `Declare` istruzione.</span><span class="sxs-lookup"><span data-stu-id="8e58a-103">A dynamic-link library (DLL) is a library specified in the `Lib` clause of a `Declare` statement.</span></span> <span data-ttu-id="8e58a-104">Le possibili cause di questo errore includono:</span><span class="sxs-lookup"><span data-stu-id="8e58a-104">Possible causes for this error include:</span></span>  
  
- <span data-ttu-id="8e58a-105">Il file non è un file eseguibile DLL.</span><span class="sxs-lookup"><span data-stu-id="8e58a-105">The file is not DLL executable.</span></span>  
  
- <span data-ttu-id="8e58a-106">Il file non è una DLL di Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="8e58a-106">The file is not a Microsoft Windows DLL.</span></span>  
  
- <span data-ttu-id="8e58a-107">La DLL fa riferimento a un'altra DLL non presente.</span><span class="sxs-lookup"><span data-stu-id="8e58a-107">The DLL references another DLL that is not present.</span></span>  
  
- <span data-ttu-id="8e58a-108">La DLL o la DLL a cui si fa riferimento non si trova in una directory specificata nel percorso.</span><span class="sxs-lookup"><span data-stu-id="8e58a-108">The DLL or referenced DLL is not in a directory specified in the path.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8e58a-109">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="8e58a-109">To correct this error</span></span>  
  
- <span data-ttu-id="8e58a-110">Se il file è un file di testo di origine e pertanto non un eseguibile DLL, è necessario compilarlo e collegarlo a un modulo eseguibile DLL.</span><span class="sxs-lookup"><span data-stu-id="8e58a-110">If the file is a source-text file and therefore not DLL executable, it must be compiled and linked to a DLL-executable form.</span></span>  
  
- <span data-ttu-id="8e58a-111">Se il file non è una DLL di Microsoft Windows, ottenere l'equivalente di Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="8e58a-111">If the file is not a Microsoft Windows DLL, obtain the Microsoft Windows equivalent.</span></span>  
  
- <span data-ttu-id="8e58a-112">Se la DLL fa riferimento a un'altra DLL non presente, ottenere la DLL a cui si fa riferimento e renderla disponibile.</span><span class="sxs-lookup"><span data-stu-id="8e58a-112">If the DLL references another DLL that is not present, obtain the referenced DLL and make it available.</span></span>  
  
- <span data-ttu-id="8e58a-113">Se la dll o la dll a cui si fa riferimento non è presente in una directory specificata dal percorso, spostare la DLL in una directory a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="8e58a-113">If the DLL or referenced DLL is not in a directory specified by the path, move the DLL to a referenced directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e58a-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8e58a-114">See also</span></span>

- [<span data-ttu-id="8e58a-115">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="8e58a-115">Declare Statement</span></span>](../statements/declare-statement.md)
