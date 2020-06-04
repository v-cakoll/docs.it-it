---
title: Errore di automazione
ms.date: 07/20/2015
f1_keywords:
- vbrID440
ms.assetid: 2c4be5c5-2f0d-4a2b-96fe-d1b24f08fc4c
ms.openlocfilehash: d62ba57db8bffefb2cfebed705251d87fe285602
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409894"
---
# <a name="automation-error"></a><span data-ttu-id="fc7ce-102">Errore di automazione</span><span class="sxs-lookup"><span data-stu-id="fc7ce-102">Automation error</span></span>

<span data-ttu-id="fc7ce-103">Si è verificato un errore durante l'esecuzione di un metodo o durante il recupero o l'impostazione di una proprietà di una variabile oggetto.</span><span class="sxs-lookup"><span data-stu-id="fc7ce-103">An error occurred while executing a method or getting or setting a property of an object variable.</span></span> <span data-ttu-id="fc7ce-104">L'errore è stato segnalato dall'applicazione che ha creato l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="fc7ce-104">The error was reported by the application that created the object.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="fc7ce-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="fc7ce-105">To correct this error</span></span>  
  
1. <span data-ttu-id="fc7ce-106">Verificare le proprietà dell'oggetto `Err` per determinare l'origine e la natura dell'errore.</span><span class="sxs-lookup"><span data-stu-id="fc7ce-106">Check the properties of the `Err` object to determine the source and nature of the error.</span></span>  
  
2. <span data-ttu-id="fc7ce-107">Usare l'istruzione `On Error Resume Next` immediatamente prima dell'istruzione di accesso e quindi controllare subito la presenza di errori dopo l'istruzione di accesso.</span><span class="sxs-lookup"><span data-stu-id="fc7ce-107">Use the `On Error Resume Next` statement immediately before the accessing statement, and then check for errors immediately after the accessing statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc7ce-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fc7ce-108">See also</span></span>

- [<span data-ttu-id="fc7ce-109">Tipi di errore</span><span class="sxs-lookup"><span data-stu-id="fc7ce-109">Error Types</span></span>](../../programming-guide/language-features/error-types.md)
- [<span data-ttu-id="fc7ce-110">Comunica con Microsoft</span><span class="sxs-lookup"><span data-stu-id="fc7ce-110">Talk to Us</span></span>](/visualstudio/ide/feedback-options)
