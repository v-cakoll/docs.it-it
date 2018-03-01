---
title: Errore di automazione
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID440
ms.assetid: 2c4be5c5-2f0d-4a2b-96fe-d1b24f08fc4c
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 790b171b8d4022bd6d8b038c4221f24805ae42f5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="automation-error"></a><span data-ttu-id="0ed79-102">Errore di automazione</span><span class="sxs-lookup"><span data-stu-id="0ed79-102">Automation error</span></span>
<span data-ttu-id="0ed79-103">Si è verificato un errore durante l'esecuzione di un metodo o durante il recupero o l'impostazione di una proprietà di una variabile oggetto.</span><span class="sxs-lookup"><span data-stu-id="0ed79-103">An error occurred while executing a method or getting or setting a property of an object variable.</span></span> <span data-ttu-id="0ed79-104">L'errore è stato segnalato dall'applicazione che ha creato l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="0ed79-104">The error was reported by the application that created the object.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="0ed79-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="0ed79-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="0ed79-106">Verificare le proprietà dell'oggetto `Err` per determinare l'origine e la natura dell'errore.</span><span class="sxs-lookup"><span data-stu-id="0ed79-106">Check the properties of the `Err` object to determine the source and nature of the error.</span></span>  
  
2.  <span data-ttu-id="0ed79-107">Usare l'istruzione `On Error Resume Next` immediatamente prima dell'istruzione di accesso e quindi controllare subito la presenza di errori dopo l'istruzione di accesso.</span><span class="sxs-lookup"><span data-stu-id="0ed79-107">Use the `On Error Resume Next` statement immediately before the accessing statement, and then check for errors immediately after the accessing statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ed79-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ed79-108">See Also</span></span>  
 [<span data-ttu-id="0ed79-109">Tipi di errore</span><span class="sxs-lookup"><span data-stu-id="0ed79-109">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)  
 [<span data-ttu-id="0ed79-110">Comunicazioni con Microsoft</span><span class="sxs-lookup"><span data-stu-id="0ed79-110">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)
