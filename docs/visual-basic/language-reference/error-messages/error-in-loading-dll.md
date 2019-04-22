---
title: Errore di caricamento della DLL (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrID48
ms.assetid: 4226cd1f-028c-477d-88a5-cb57f7e0cdc8
ms.openlocfilehash: c3f88a5a3c37c89d23055aa413957b2add38ed67
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58816902"
---
# <a name="error-in-loading-dll-visual-basic"></a><span data-ttu-id="b0131-102">Errore di caricamento della DLL (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b0131-102">Error in loading DLL (Visual Basic)</span></span>
<span data-ttu-id="b0131-103">Una libreria di collegamento dinamico (DLL) è una libreria specificata nel `Lib` clausola di un `Declare` istruzione.</span><span class="sxs-lookup"><span data-stu-id="b0131-103">A dynamic-link library (DLL) is a library specified in the `Lib` clause of a `Declare` statement.</span></span> <span data-ttu-id="b0131-104">Possibili cause di questo errore includono:</span><span class="sxs-lookup"><span data-stu-id="b0131-104">Possible causes for this error include:</span></span>  
  
-   <span data-ttu-id="b0131-105">Il file non è un eseguibile DLL.</span><span class="sxs-lookup"><span data-stu-id="b0131-105">The file is not DLL executable.</span></span>  
  
-   <span data-ttu-id="b0131-106">Il file non è una DLL di Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="b0131-106">The file is not a Microsoft Windows DLL.</span></span>  
  
-   <span data-ttu-id="b0131-107">La DLL fa riferimento a un'altra DLL che non è presente.</span><span class="sxs-lookup"><span data-stu-id="b0131-107">The DLL references another DLL that is not present.</span></span>  
  
-   <span data-ttu-id="b0131-108">La DLL o cui si fa riferimento non è in una directory specificata nel percorso.</span><span class="sxs-lookup"><span data-stu-id="b0131-108">The DLL or referenced DLL is not in a directory specified in the path.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b0131-109">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="b0131-109">To correct this error</span></span>  
  
-   <span data-ttu-id="b0131-110">Se il file è un file di testo di origine e pertanto non eseguibile DLL, deve essere compilato e collegato a un modulo DLL-file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="b0131-110">If the file is a source-text file and therefore not DLL executable, it must be compiled and linked to a DLL-executable form.</span></span>  
  
-   <span data-ttu-id="b0131-111">Se il file non è una DLL di Microsoft Windows, ottenere l'equivalente di Windows Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b0131-111">If the file is not a Microsoft Windows DLL, obtain the Microsoft Windows equivalent.</span></span>  
  
-   <span data-ttu-id="b0131-112">Se la DLL fa riferimento a un'altra DLL che non è presente, ottenere la DLL di cui viene fatto riferimento e renderlo disponibile.</span><span class="sxs-lookup"><span data-stu-id="b0131-112">If the DLL references another DLL that is not present, obtain the referenced DLL and make it available.</span></span>  
  
-   <span data-ttu-id="b0131-113">Se la DLL o cui si fa riferimento non è in una directory specificata dal percorso, spostare la DLL in una directory di cui viene fatto riferimento.</span><span class="sxs-lookup"><span data-stu-id="b0131-113">If the DLL or referenced DLL is not in a directory specified by the path, move the DLL to a referenced directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0131-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b0131-114">See also</span></span>

- [<span data-ttu-id="b0131-115">Istruzione Declare</span><span class="sxs-lookup"><span data-stu-id="b0131-115">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
