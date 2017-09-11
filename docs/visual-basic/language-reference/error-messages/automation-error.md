---
title: Errore di automazione | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID440
dev_langs:
- VB
ms.assetid: 2c4be5c5-2f0d-4a2b-96fe-d1b24f08fc4c
caps.latest.revision: 9
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
ms.openlocfilehash: b48ada07663889db633a43fabb577d5129c5cbb3
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="automation-error"></a><span data-ttu-id="e4e17-102">Errore di automazione</span><span class="sxs-lookup"><span data-stu-id="e4e17-102">Automation error</span></span>
<span data-ttu-id="e4e17-103">Si è verificato un errore durante l'esecuzione di un metodo o durante il recupero o l'impostazione di una proprietà di una variabile oggetto.</span><span class="sxs-lookup"><span data-stu-id="e4e17-103">An error occurred while executing a method or getting or setting a property of an object variable.</span></span> <span data-ttu-id="e4e17-104">L'errore è stato segnalato dall'applicazione che ha creato l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="e4e17-104">The error was reported by the application that created the object.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e4e17-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="e4e17-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="e4e17-106">Verificare le proprietà dell'oggetto `Err` per determinare l'origine e la natura dell'errore.</span><span class="sxs-lookup"><span data-stu-id="e4e17-106">Check the properties of the `Err` object to determine the source and nature of the error.</span></span>  
  
2.  <span data-ttu-id="e4e17-107">Usare l'istruzione `On Error Resume Next` immediatamente prima dell'istruzione di accesso e quindi controllare subito la presenza di errori dopo l'istruzione di accesso.</span><span class="sxs-lookup"><span data-stu-id="e4e17-107">Use the `On Error Resume Next` statement immediately before the accessing statement, and then check for errors immediately after the accessing statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4e17-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4e17-108">See Also</span></span>  
 <span data-ttu-id="e4e17-109">[Tipi di errore](../../../visual-basic/programming-guide/language-features/error-types.md) </span><span class="sxs-lookup"><span data-stu-id="e4e17-109">[Error Types](../../../visual-basic/programming-guide/language-features/error-types.md) </span></span>  
<span data-ttu-id="e4e17-110"> [Comunicazioni con Microsoft](https://docs.microsoft.com/visualstudio/ide/talk-to-us)</span><span class="sxs-lookup"><span data-stu-id="e4e17-110"> [Talk to Us](https://docs.microsoft.com/visualstudio/ide/talk-to-us)</span></span>
