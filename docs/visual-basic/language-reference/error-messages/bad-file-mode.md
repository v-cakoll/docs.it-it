---
title: Modalità file non valida
ms.date: 07/20/2015
f1_keywords:
- vbrID54
ms.assetid: 74891e96-884b-4c8d-872d-cd11ae272372
ms.openlocfilehash: 534ea2d8316dc29cace798c5ad9b7697a290026f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409869"
---
# <a name="bad-file-mode"></a><span data-ttu-id="d1348-102">Modalità file non valida</span><span class="sxs-lookup"><span data-stu-id="d1348-102">Bad file mode</span></span>
<span data-ttu-id="d1348-103">Le istruzioni utilizzate per manipolare il contenuto del file devono essere appropriate per la modalità in cui il file è stato aperto.</span><span class="sxs-lookup"><span data-stu-id="d1348-103">Statements used in manipulating file contents must be appropriate to the mode in which the file was opened.</span></span> <span data-ttu-id="d1348-104">Le cause possibili includono:</span><span class="sxs-lookup"><span data-stu-id="d1348-104">Possible causes include:</span></span>  
  
- <span data-ttu-id="d1348-105">Un' `FilePutObject` `FileGetObject` istruzione o specifica un file sequenziale.</span><span class="sxs-lookup"><span data-stu-id="d1348-105">A `FilePutObject` or `FileGetObject` statement specifies a sequential file.</span></span>  
  
- <span data-ttu-id="d1348-106">Un' `Print` istruzione specifica un file aperto per una modalità di accesso diversa da `Output` o `Append` .</span><span class="sxs-lookup"><span data-stu-id="d1348-106">A `Print` statement specifies a file opened for an access mode other than `Output` or `Append`.</span></span>  
  
- <span data-ttu-id="d1348-107">Un' `Input` istruzione specifica un file aperto per una modalità di accesso diversa da`Input`</span><span class="sxs-lookup"><span data-stu-id="d1348-107">An `Input` statement specifies a file opened for an access mode other than `Input`</span></span>  
  
- <span data-ttu-id="d1348-108">Tentativo di scrittura in un file di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="d1348-108">An attempt to write to a read-only file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d1348-109">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="d1348-109">To correct this error</span></span>  
  
- <span data-ttu-id="d1348-110">Assicurarsi `FilePutObject` che e facciano `FileGetObject` riferimento solo ai file aperti per `Random` `Binary` l'accesso o.</span><span class="sxs-lookup"><span data-stu-id="d1348-110">Make sure `FilePutObject` and `FileGetObject` are only referring to files open for `Random` or `Binary` access.</span></span>  
  
- <span data-ttu-id="d1348-111">Assicurarsi `Print` di specificare un file aperto per la `Output` `Append` modalità di accesso o.</span><span class="sxs-lookup"><span data-stu-id="d1348-111">Make sure `Print` specifies a file opened for either `Output` or `Append` access mode.</span></span> <span data-ttu-id="d1348-112">In caso contrario, utilizzare un'istruzione diversa per inserire i dati nel file o riaprire il file in una modalità appropriata.</span><span class="sxs-lookup"><span data-stu-id="d1348-112">If not, use a different statement to place data in the file, or reopen the file in an appropriate mode.</span></span>  
  
- <span data-ttu-id="d1348-113">Assicurarsi `Input` di specificare un file aperto per `Input` .</span><span class="sxs-lookup"><span data-stu-id="d1348-113">Make sure `Input` specifies a file opened for `Input`.</span></span> <span data-ttu-id="d1348-114">In caso contrario, utilizzare un'istruzione diversa per inserire i dati nel file o riaprire il file in una modalità appropriata.</span><span class="sxs-lookup"><span data-stu-id="d1348-114">If not, use a different statement to place data in the file or reopen the file in an appropriate mode.</span></span>  
  
- <span data-ttu-id="d1348-115">Se si sta scrivendo in un file di sola lettura, modificare lo stato di lettura/scrittura del file o non tentare di scrivervi.</span><span class="sxs-lookup"><span data-stu-id="d1348-115">If you are writing to a read-only file, change the read/write status of the file or do not try to write to it.</span></span>  
  
- <span data-ttu-id="d1348-116">Usare la funzionalità disponibile nell'oggetto `My.Computer.FileSystem` .</span><span class="sxs-lookup"><span data-stu-id="d1348-116">Use the functionality available in the `My.Computer.FileSystem` object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1348-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d1348-117">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem>
- [<span data-ttu-id="d1348-118">Risoluzione dei problemi: Lettura e scrittura nei file di testo</span><span class="sxs-lookup"><span data-stu-id="d1348-118">Troubleshooting: Reading from and Writing to Text Files</span></span>](../../developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)
