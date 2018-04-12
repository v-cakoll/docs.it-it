---
title: Errore di accesso percorso File
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID75
ms.assetid: 6ce3a161-7316-46bd-a785-0d50e5414020
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2c86d46c884617be152a5954426e9ddd6ef61651
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="pathfile-access-error"></a><span data-ttu-id="88e16-102">Errore di accesso al percorso/file</span><span class="sxs-lookup"><span data-stu-id="88e16-102">Path/File access error</span></span>
<span data-ttu-id="88e16-103">Durante un'operazione di accesso ai file o l'accesso al disco, il sistema operativo non può stabilire una connessione tra il percorso e il nome del file.</span><span class="sxs-lookup"><span data-stu-id="88e16-103">During a file-access or disk-access operation, the operating system could not make a connection between the path and the file name.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="88e16-104">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="88e16-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="88e16-105">Verificare che la specifica del file è formattata correttamente.</span><span class="sxs-lookup"><span data-stu-id="88e16-105">Make sure the file specification is correctly formatted.</span></span> <span data-ttu-id="88e16-106">Un nome di file può contenere un nome completo (assoluto) o il relativo percorso.</span><span class="sxs-lookup"><span data-stu-id="88e16-106">A file name can contain a fully qualified (absolute) or relative path.</span></span> <span data-ttu-id="88e16-107">Il percorso completo inizia con il nome dell'unità (se il percorso in un'altra unità) ed elenca il percorso dalla radice esplicito al file.</span><span class="sxs-lookup"><span data-stu-id="88e16-107">A fully qualified path starts with the drive name (if the path is on another drive) and lists the explicit path from the root to the file.</span></span> <span data-ttu-id="88e16-108">Qualsiasi percorso che non è completo è relativo unità corrente e la directory.</span><span class="sxs-lookup"><span data-stu-id="88e16-108">Any path that is not fully qualified is relative to the current drive and directory.</span></span>  
  
2.  <span data-ttu-id="88e16-109">Assicurarsi che non si ha provato a salvare un file che sostituirà un file di sola lettura esistente.</span><span class="sxs-lookup"><span data-stu-id="88e16-109">Make sure that you did not attempt to save a file that would replace an existing read-only file.</span></span> <span data-ttu-id="88e16-110">In questo caso, modificare l'attributo di sola lettura del file di destinazione o salvare il file con un nome file diverso.</span><span class="sxs-lookup"><span data-stu-id="88e16-110">If this is the case, change the read-only attribute of the target file, or save the file with a different file name.</span></span>  
  
3.  <span data-ttu-id="88e16-111">Assicurarsi che si non tenta di aprire un file di sola lettura in sequenziale `Output` o `Append` modalità.</span><span class="sxs-lookup"><span data-stu-id="88e16-111">Make sure you did not attempt to open a read-only file in sequential `Output` or `Append` mode.</span></span> <span data-ttu-id="88e16-112">In questo caso, aprire il file in `Input` modalità o modificare l'attributo di sola lettura del file.</span><span class="sxs-lookup"><span data-stu-id="88e16-112">If this is the case, open the file in `Input` mode or change the read-only attribute of the file.</span></span>  
  
4.  <span data-ttu-id="88e16-113">Assicurarsi che non si ha provato a modificare un [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] progetto all'interno di un database o un documento.</span><span class="sxs-lookup"><span data-stu-id="88e16-113">Make sure you did not attempt to change a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] project within a database or document.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88e16-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="88e16-114">See Also</span></span>  
 [<span data-ttu-id="88e16-115">Tipi di errore</span><span class="sxs-lookup"><span data-stu-id="88e16-115">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
