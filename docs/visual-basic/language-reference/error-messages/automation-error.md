---
title: Errore di automazione
ms.date: 07/20/2015
f1_keywords:
- vbrID440
ms.assetid: 2c4be5c5-2f0d-4a2b-96fe-d1b24f08fc4c
ms.openlocfilehash: e0ebaabb14cf5685469f88b0be3b7fece017165e
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58843656"
---
# <a name="automation-error"></a><span data-ttu-id="3be6d-102">Errore di automazione</span><span class="sxs-lookup"><span data-stu-id="3be6d-102">Automation error</span></span>
<span data-ttu-id="3be6d-103">Si è verificato un errore durante l'esecuzione di un metodo o durante il recupero o l'impostazione di una proprietà di una variabile oggetto.</span><span class="sxs-lookup"><span data-stu-id="3be6d-103">An error occurred while executing a method or getting or setting a property of an object variable.</span></span> <span data-ttu-id="3be6d-104">L'errore è stato segnalato dall'applicazione che ha creato l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="3be6d-104">The error was reported by the application that created the object.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3be6d-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="3be6d-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="3be6d-106">Verificare le proprietà dell'oggetto `Err` per determinare l'origine e la natura dell'errore.</span><span class="sxs-lookup"><span data-stu-id="3be6d-106">Check the properties of the `Err` object to determine the source and nature of the error.</span></span>  
  
2.  <span data-ttu-id="3be6d-107">Usare l'istruzione `On Error Resume Next` immediatamente prima dell'istruzione di accesso e quindi controllare subito la presenza di errori dopo l'istruzione di accesso.</span><span class="sxs-lookup"><span data-stu-id="3be6d-107">Use the `On Error Resume Next` statement immediately before the accessing statement, and then check for errors immediately after the accessing statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3be6d-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3be6d-108">See also</span></span>

- [<span data-ttu-id="3be6d-109">Tipi di errore</span><span class="sxs-lookup"><span data-stu-id="3be6d-109">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
- <span data-ttu-id="3be6d-110">[Talk to Us](/visualstudio/ide/talk-to-us) (Comunicazioni con Microsoft)</span><span class="sxs-lookup"><span data-stu-id="3be6d-110">[Talk to Us](/visualstudio/ide/talk-to-us)</span></span>
