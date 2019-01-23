---
title: Errore di accesso percorso-File
ms.date: 07/20/2015
f1_keywords:
- vbrID75
ms.assetid: 6ce3a161-7316-46bd-a785-0d50e5414020
ms.openlocfilehash: 53f021faa9e4ae69a71d825ca823e1180421afc6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54522479"
---
# <a name="pathfile-access-error"></a><span data-ttu-id="4e3b1-102">Errore di accesso al percorso/file</span><span class="sxs-lookup"><span data-stu-id="4e3b1-102">Path/File access error</span></span>
<span data-ttu-id="4e3b1-103">Durante un'operazione di accesso ai file o di accesso al disco del sistema operativo non è stato possibile stabilire una connessione tra il percorso e il nome del file.</span><span class="sxs-lookup"><span data-stu-id="4e3b1-103">During a file-access or disk-access operation, the operating system could not make a connection between the path and the file name.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4e3b1-104">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="4e3b1-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="4e3b1-105">Assicurarsi che la specifica del file è formattata correttamente.</span><span class="sxs-lookup"><span data-stu-id="4e3b1-105">Make sure the file specification is correctly formatted.</span></span> <span data-ttu-id="4e3b1-106">Un nome di file può contenere un nome completo (assoluto) o il relativo percorso.</span><span class="sxs-lookup"><span data-stu-id="4e3b1-106">A file name can contain a fully qualified (absolute) or relative path.</span></span> <span data-ttu-id="4e3b1-107">Il percorso completo inizia con il nome dell'unità (se il percorso in un'unità diversa) ed elenca il percorso esplicito dalla radice del file.</span><span class="sxs-lookup"><span data-stu-id="4e3b1-107">A fully qualified path starts with the drive name (if the path is on another drive) and lists the explicit path from the root to the file.</span></span> <span data-ttu-id="4e3b1-108">Qualsiasi percorso che non è completo è relativo alla unità corrente e della directory.</span><span class="sxs-lookup"><span data-stu-id="4e3b1-108">Any path that is not fully qualified is relative to the current drive and directory.</span></span>  
  
2.  <span data-ttu-id="4e3b1-109">Assicurarsi che non si ha provato a salvare un file sostituirà un file di sola lettura esistente.</span><span class="sxs-lookup"><span data-stu-id="4e3b1-109">Make sure that you did not attempt to save a file that would replace an existing read-only file.</span></span> <span data-ttu-id="4e3b1-110">In questo caso, modificare l'attributo di sola lettura del file di destinazione o salvare il file con un nome file diverso.</span><span class="sxs-lookup"><span data-stu-id="4e3b1-110">If this is the case, change the read-only attribute of the target file, or save the file with a different file name.</span></span>  
  
3.  <span data-ttu-id="4e3b1-111">Assicurarsi che non si ha provato a aprire un file di sola lettura sequenziale `Output` o `Append` modalità.</span><span class="sxs-lookup"><span data-stu-id="4e3b1-111">Make sure you did not attempt to open a read-only file in sequential `Output` or `Append` mode.</span></span> <span data-ttu-id="4e3b1-112">In questo caso, aprire il file in `Input` modalità o modifica l'attributo di sola lettura del file.</span><span class="sxs-lookup"><span data-stu-id="4e3b1-112">If this is the case, open the file in `Input` mode or change the read-only attribute of the file.</span></span>  
  
4.  <span data-ttu-id="4e3b1-113">Assicurarsi che non si ha provato a modificare un progetto di Visual Basic all'interno di un database o un documento.</span><span class="sxs-lookup"><span data-stu-id="4e3b1-113">Make sure you did not attempt to change a Visual Basic project within a database or document.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e3b1-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4e3b1-114">See also</span></span>
- [<span data-ttu-id="4e3b1-115">Tipi di errore</span><span class="sxs-lookup"><span data-stu-id="4e3b1-115">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
