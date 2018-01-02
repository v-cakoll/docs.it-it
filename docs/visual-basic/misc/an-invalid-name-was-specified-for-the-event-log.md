---
title: "È stato specificato un nome non valido per il log eventi"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: b1b158bd-f13f-4371-a8af-31c0e86ae6be
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 76e4082710a6786ec5e743ce606e849637c26512
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/21/2017
---
# <a name="an-invalid-name-was-specified-for-the-event-log"></a><span data-ttu-id="2171e-102">È stato specificato un nome non valido per il log eventi</span><span class="sxs-lookup"><span data-stu-id="2171e-102">An invalid name was specified for the event log</span></span>
<span data-ttu-id="2171e-103">È stato specificato un nome non valido per il log eventi.</span><span class="sxs-lookup"><span data-stu-id="2171e-103">An invalid name was specified for the event log.</span></span> <span data-ttu-id="2171e-104">Generalmente è l'effetto della presenza di caratteri non validi nel nome, di un nome file vuoto o di un nome file troppo lungo.</span><span class="sxs-lookup"><span data-stu-id="2171e-104">Usually this is a result of invalid characters in the name, a blank file name, or a file name that is too long.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2171e-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="2171e-105">To correct this error</span></span>  
  
-   <span data-ttu-id="2171e-106">Se la lunghezza del nome specificato supera otto caratteri, accertarsi che non vi sia un conflitto con i nomi di altri log eventi.</span><span class="sxs-lookup"><span data-stu-id="2171e-106">If the specified name is more than eight characters, make sure there is no conflict with the names of other event logs.</span></span> <span data-ttu-id="2171e-107">Quando si determina se il nome è univoco vengono presi in considerazione solo i primi otto caratteri.</span><span class="sxs-lookup"><span data-stu-id="2171e-107">Only the first eight characters are evaluated when determining if the name is unique.</span></span>  
  
-   <span data-ttu-id="2171e-108">Se si fornisce un percorso, accertarsi che venga analizzato correttamente.</span><span class="sxs-lookup"><span data-stu-id="2171e-108">If supplying a path, make sure it is parsed correctly.</span></span>  
  
-   <span data-ttu-id="2171e-109">Verificare che il nome non contenga caratteri non validi.</span><span class="sxs-lookup"><span data-stu-id="2171e-109">Check that there are no invalid characters in the name.</span></span> <span data-ttu-id="2171e-110">I caratteri che non è possibile usare in un nome file comprendono `<`, `>`, `:`, `"`, `/`, `\`e `|`.</span><span class="sxs-lookup"><span data-stu-id="2171e-110">Characters that cannot be used in a file name include `<`, `>`, `:`, `"`, `/`, `\`, and `|`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2171e-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2171e-111">See Also</span></span>  
 [<span data-ttu-id="2171e-112">Procedura: analizzare percorsi di file</span><span class="sxs-lookup"><span data-stu-id="2171e-112">How to: Parse File Paths</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)  
 [<span data-ttu-id="2171e-113">Procedura: rinominare un file</span><span class="sxs-lookup"><span data-stu-id="2171e-113">How to: Rename a File</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-rename-a-file.md)  
 
