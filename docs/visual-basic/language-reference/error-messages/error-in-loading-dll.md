---
title: Errore di caricamento della DLL (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrID48
ms.assetid: 4226cd1f-028c-477d-88a5-cb57f7e0cdc8
ms.openlocfilehash: ac21c4d52b248025ee26bac3e511bb5b0a0b668e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33584683"
---
# <a name="error-in-loading-dll-visual-basic"></a><span data-ttu-id="72514-102">Errore di caricamento della DLL (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="72514-102">Error in loading DLL (Visual Basic)</span></span>
<span data-ttu-id="72514-103">Una libreria di collegamento dinamico (DLL) è una libreria specificata nel `Lib` clausola di un `Declare` istruzione.</span><span class="sxs-lookup"><span data-stu-id="72514-103">A dynamic-link library (DLL) is a library specified in the `Lib` clause of a `Declare` statement.</span></span> <span data-ttu-id="72514-104">Possibili cause di questo errore includono:</span><span class="sxs-lookup"><span data-stu-id="72514-104">Possible causes for this error include:</span></span>  
  
-   <span data-ttu-id="72514-105">Il file non è un eseguibile DLL.</span><span class="sxs-lookup"><span data-stu-id="72514-105">The file is not DLL executable.</span></span>  
  
-   <span data-ttu-id="72514-106">Il file non è una DLL di Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="72514-106">The file is not a Microsoft Windows DLL.</span></span>  
  
-   <span data-ttu-id="72514-107">La DLL fa riferimento a un'altra DLL che non è presente.</span><span class="sxs-lookup"><span data-stu-id="72514-107">The DLL references another DLL that is not present.</span></span>  
  
-   <span data-ttu-id="72514-108">La DLL o riferimento non è in una directory specificata nel percorso.</span><span class="sxs-lookup"><span data-stu-id="72514-108">The DLL or referenced DLL is not in a directory specified in the path.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="72514-109">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="72514-109">To correct this error</span></span>  
  
-   <span data-ttu-id="72514-110">Se il file è un file di testo di origine e pertanto non eseguibile DLL, deve essere compilato e collegato a un modulo eseguibile DLL.</span><span class="sxs-lookup"><span data-stu-id="72514-110">If the file is a source-text file and therefore not DLL executable, it must be compiled and linked to a DLL-executable form.</span></span>  
  
-   <span data-ttu-id="72514-111">Se il file non è una DLL di Microsoft Windows, è possibile ottenere l'equivalente di Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="72514-111">If the file is not a Microsoft Windows DLL, obtain the Microsoft Windows equivalent.</span></span>  
  
-   <span data-ttu-id="72514-112">Se la DLL fa riferimento a un'altra DLL che non è presente, ottenere la DLL di cui viene fatto riferimento e renderli disponibili.</span><span class="sxs-lookup"><span data-stu-id="72514-112">If the DLL references another DLL that is not present, obtain the referenced DLL and make it available.</span></span>  
  
-   <span data-ttu-id="72514-113">Se la DLL o riferimento non è in una directory specificata dal percorso, spostare il file DLL in una directory a cui fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="72514-113">If the DLL or referenced DLL is not in a directory specified by the path, move the DLL to a referenced directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72514-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="72514-114">See Also</span></span>  
 [<span data-ttu-id="72514-115">Istruzione Declare</span><span class="sxs-lookup"><span data-stu-id="72514-115">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
