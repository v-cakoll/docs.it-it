---
title: Lunghezza del record non valida
ms.date: 07/20/2015
f1_keywords:
- vbrID59
ms.assetid: 0926a3a4-177b-4452-9b33-d8a01e24cc21
ms.openlocfilehash: 1bc75303bcc2f46e54c06e89347da28997e59786
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2019
ms.locfileid: "59979739"
---
# <a name="bad-record-length"></a><span data-ttu-id="f4ba0-102">Lunghezza del record non valida</span><span class="sxs-lookup"><span data-stu-id="f4ba0-102">Bad record length</span></span>
<span data-ttu-id="f4ba0-103">Di seguito sono riportate le cause possibili dell'errore:</span><span class="sxs-lookup"><span data-stu-id="f4ba0-103">Among the possible causes of this error are:</span></span>  
  
-   <span data-ttu-id="f4ba0-104">La lunghezza di una variabile di record specificata in un `FileGet`, `FileGetObject`, `FilePut` oppure `FilePutObject` istruzione è diversa da quella specificata nel corrispondente `FileOpen` istruzione.</span><span class="sxs-lookup"><span data-stu-id="f4ba0-104">The length of a record variable specified in a `FileGet`, `FileGetObject`, `FilePut` or `FilePutObject` statement differs from the length specified in the corresponding `FileOpen` statement.</span></span>  
  
-   <span data-ttu-id="f4ba0-105">La variabile in un `FilePut` o `FilePutObject` o istruzione include una stringa a lunghezza variabile.</span><span class="sxs-lookup"><span data-stu-id="f4ba0-105">The variable in a `FilePut` or `FilePutObject` statement is or includes a variable-length string.</span></span>  
  
-   <span data-ttu-id="f4ba0-106">La variabile in un `FilePut` oppure `FilePutObject` è o include un `Variant` tipo.</span><span class="sxs-lookup"><span data-stu-id="f4ba0-106">The variable in a `FilePut` or `FilePutObject` is or includes a `Variant` type.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f4ba0-107">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="f4ba0-107">To correct this error</span></span>  
  
1. <span data-ttu-id="f4ba0-108">Assicurarsi che la somma delle dimensioni delle variabili di lunghezza fissa nel tipo definito dall'utente che definisce il record del tipo di variabile è uguale al valore indicato nel `FileOpen` dell'istruzione `Len` clausola.</span><span class="sxs-lookup"><span data-stu-id="f4ba0-108">Make sure the sum of the sizes of fixed-length variables in the user-defined type defining the record variable's type is the same as the value stated in the `FileOpen` statement's `Len` clause.</span></span>  
  
2. <span data-ttu-id="f4ba0-109">Se la variabile in un `FilePut` o `FilePutObject` o istruzione include una stringa a lunghezza variabile, assicurarsi che la stringa di lunghezza variabile sia di almeno 2 caratteri più la lunghezza del record specificata nel breve il `Len` clausola del `FileOpen` istruzione.</span><span class="sxs-lookup"><span data-stu-id="f4ba0-109">If the variable in a `FilePut` or `FilePutObject` statement is or includes a variable-length string, make sure the variable-length string is at least 2 characters shorter than the record length specified in the `Len` clause of the `FileOpen` statement.</span></span>  
  
3. <span data-ttu-id="f4ba0-110">Se la variabile in un `FilePut` o `FilePutObject` è o include un `Variant` assicurarsi che la stringa di lunghezza variabile è almeno 4 byte più la lunghezza del record specificata nel breve il `Len` clausola del `FileOpen` istruzione.</span><span class="sxs-lookup"><span data-stu-id="f4ba0-110">If the variable in a `FilePut` or `FilePutObject` is or includes a `Variant` make sure the variable-length string is at least 4 bytes shorter than the record length specified in the `Len` clause of the `FileOpen` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4ba0-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f4ba0-111">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.FileGet%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FileGetObject%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FilePut%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FilePutObject%2A>
