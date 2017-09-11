---
title: Errore di accesso percorso-File | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID75
dev_langs:
- VB
ms.assetid: 6ce3a161-7316-46bd-a785-0d50e5414020
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 6307c0d0115e3791d5ad6bf4243057e6ed90d9cd
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="pathfile-access-error"></a><span data-ttu-id="bcb54-102">Errore di accesso al percorso/file</span><span class="sxs-lookup"><span data-stu-id="bcb54-102">Path/File access error</span></span>
<span data-ttu-id="bcb54-103">Durante un'operazione di accesso ai file o l'accesso al disco, il sistema operativo non ha potuto fare una connessione tra il percorso e il nome del file.</span><span class="sxs-lookup"><span data-stu-id="bcb54-103">During a file-access or disk-access operation, the operating system could not make a connection between the path and the file name.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="bcb54-104">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="bcb54-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="bcb54-105">Assicurarsi che la specifica del file è formattata correttamente.</span><span class="sxs-lookup"><span data-stu-id="bcb54-105">Make sure the file specification is correctly formatted.</span></span> <span data-ttu-id="bcb54-106">Un nome file può contenere un nome completo (assoluto) o il relativo percorso.</span><span class="sxs-lookup"><span data-stu-id="bcb54-106">A file name can contain a fully qualified (absolute) or relative path.</span></span> <span data-ttu-id="bcb54-107">Il percorso completo inizia con il nome dell'unità (se il percorso in un'altra unità) ed elenca il percorso esplicito dalla radice del file.</span><span class="sxs-lookup"><span data-stu-id="bcb54-107">A fully qualified path starts with the drive name (if the path is on another drive) and lists the explicit path from the root to the file.</span></span> <span data-ttu-id="bcb54-108">Qualsiasi percorso che non è completo è relativo l'unità corrente e la directory.</span><span class="sxs-lookup"><span data-stu-id="bcb54-108">Any path that is not fully qualified is relative to the current drive and directory.</span></span>  
  
2.  <span data-ttu-id="bcb54-109">Assicurarsi che non si tenta di salvare un file che è necessario sostituire un file di sola lettura esistente.</span><span class="sxs-lookup"><span data-stu-id="bcb54-109">Make sure that you did not attempt to save a file that would replace an existing read-only file.</span></span> <span data-ttu-id="bcb54-110">In questo caso, modificare l'attributo di sola lettura del file di destinazione o salvare il file con un nome file diverso.</span><span class="sxs-lookup"><span data-stu-id="bcb54-110">If this is the case, change the read-only attribute of the target file, or save the file with a different file name.</span></span>  
  
3.  <span data-ttu-id="bcb54-111">Assicurarsi di non aver tentato di aprire un file di sola lettura in sequenza`Output`o `Append` modalità.</span><span class="sxs-lookup"><span data-stu-id="bcb54-111">Make sure you did not attempt to open a read-only file in sequential`Output`or `Append` mode.</span></span> <span data-ttu-id="bcb54-112">In questo caso, aprire il file in `Input` modalità o modifica l'attributo di sola lettura del file.</span><span class="sxs-lookup"><span data-stu-id="bcb54-112">If this is the case, open the file in `Input` mode or change the read-only attribute of the file.</span></span>  
  
4.  <span data-ttu-id="bcb54-113">Assicurarsi di non aver tentato di modificare un [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] progetto all'interno di un database o un documento.</span><span class="sxs-lookup"><span data-stu-id="bcb54-113">Make sure you did not attempt to change a [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] project within a database or document.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcb54-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bcb54-114">See Also</span></span>  
 [<span data-ttu-id="bcb54-115">Tipi di errore</span><span class="sxs-lookup"><span data-stu-id="bcb54-115">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
