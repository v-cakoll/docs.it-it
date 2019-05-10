---
title: Modalità file non valida
ms.date: 07/20/2015
f1_keywords:
- vbrID54
ms.assetid: 74891e96-884b-4c8d-872d-cd11ae272372
ms.openlocfilehash: 9a59faf1b6f845858e36efcabdf0758e41ad75dc
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64619742"
---
# <a name="bad-file-mode"></a><span data-ttu-id="5a523-102">Modalità file non valida</span><span class="sxs-lookup"><span data-stu-id="5a523-102">Bad file mode</span></span>
<span data-ttu-id="5a523-103">Istruzioni utilizzate nella manipolazione di contenuto del file devono essere appropriate per la modalità in cui è stato aperto il file.</span><span class="sxs-lookup"><span data-stu-id="5a523-103">Statements used in manipulating file contents must be appropriate to the mode in which the file was opened.</span></span> <span data-ttu-id="5a523-104">Fra le cause possibili vi sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="5a523-104">Possible causes include:</span></span>  
  
- <span data-ttu-id="5a523-105">Oggetto `FilePutObject` o `FileGetObject` istruzione specifica un file sequenziale.</span><span class="sxs-lookup"><span data-stu-id="5a523-105">A `FilePutObject` or `FileGetObject` statement specifies a sequential file.</span></span>  
  
- <span data-ttu-id="5a523-106">Oggetto `Print` istruzione specifica un file aperto per la modalità di accesso diverso da `Output` o `Append`.</span><span class="sxs-lookup"><span data-stu-id="5a523-106">A `Print` statement specifies a file opened for an access mode other than `Output` or `Append`.</span></span>  
  
- <span data-ttu-id="5a523-107">Un `Input` istruzione specifica un file aperto per la modalità di accesso diverso da `Input`</span><span class="sxs-lookup"><span data-stu-id="5a523-107">An `Input` statement specifies a file opened for an access mode other than `Input`</span></span>  
  
- <span data-ttu-id="5a523-108">Un tentativo di scrivere in un file di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="5a523-108">An attempt to write to a read-only file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5a523-109">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="5a523-109">To correct this error</span></span>  
  
- <span data-ttu-id="5a523-110">Assicurarsi che `FilePutObject` e `FileGetObject` facciano riferimento solo a file aperti per `Random` o `Binary` accesso.</span><span class="sxs-lookup"><span data-stu-id="5a523-110">Make sure `FilePutObject` and `FileGetObject` are only referring to files open for `Random` or `Binary` access.</span></span>  
  
- <span data-ttu-id="5a523-111">Assicurarsi che `Print` specifica un file aperto per la `Output` o `Append` modalità di accesso.</span><span class="sxs-lookup"><span data-stu-id="5a523-111">Make sure `Print` specifies a file opened for either `Output` or `Append` access mode.</span></span> <span data-ttu-id="5a523-112">In caso contrario, utilizzare un'istruzione diversi per inserire dati nel file o riaprire il file in una modalità appropriata.</span><span class="sxs-lookup"><span data-stu-id="5a523-112">If not, use a different statement to place data in the file, or reopen the file in an appropriate mode.</span></span>  
  
- <span data-ttu-id="5a523-113">Assicurarsi che `Input` specifica un file aperto per `Input`.</span><span class="sxs-lookup"><span data-stu-id="5a523-113">Make sure `Input` specifies a file opened for `Input`.</span></span> <span data-ttu-id="5a523-114">In caso contrario, utilizzare un'istruzione diversi per inserire dati nel file o riaprire il file in una modalità appropriata.</span><span class="sxs-lookup"><span data-stu-id="5a523-114">If not, use a different statement to place data in the file or reopen the file in an appropriate mode.</span></span>  
  
- <span data-ttu-id="5a523-115">Se si scrive in un file di sola lettura, modificare lo stato di lettura/scrittura del file o non tentare di scrivervi.</span><span class="sxs-lookup"><span data-stu-id="5a523-115">If you are writing to a read-only file, change the read/write status of the file or do not try to write to it.</span></span>  
  
- <span data-ttu-id="5a523-116">Usare la funzionalità disponibile nell'oggetto `My.Computer.FileSystem` .</span><span class="sxs-lookup"><span data-stu-id="5a523-116">Use the functionality available in the `My.Computer.FileSystem` object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a523-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5a523-117">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem>
- [<span data-ttu-id="5a523-118">Risoluzione dei problemi: Lettura e scrittura nei file di testo</span><span class="sxs-lookup"><span data-stu-id="5a523-118">Troubleshooting: Reading from and Writing to Text Files</span></span>](../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)
