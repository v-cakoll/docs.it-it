---
title: Autorizzazione negata (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID70
ms.assetid: 71f46756-f522-4814-aab4-492bf9924245
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c5d7965ebd42cb3e56d66966d035be9ba3d3957c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="permission-denied-visual-basic"></a><span data-ttu-id="5f2ba-102">Autorizzazione negata (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5f2ba-102">Permission denied (Visual Basic)</span></span>
<span data-ttu-id="5f2ba-103">È stato effettuato un tentativo di scrivere su un disco protetto da scrittura o accedere a un file bloccato.</span><span class="sxs-lookup"><span data-stu-id="5f2ba-103">An attempt was made to write to a write-protected disk or to access a locked file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5f2ba-104">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="5f2ba-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="5f2ba-105">Per aprire un file protetto da scrittura, modificare l'attributo di protezione da scrittura del file.</span><span class="sxs-lookup"><span data-stu-id="5f2ba-105">To open a write-protected file, change the write-protection attribute of the file.</span></span>  
  
2.  <span data-ttu-id="5f2ba-106">Assicurarsi che un altro processo non ha bloccato il file e attendere per aprire il file fino a quando non lo rilascia altro processo.</span><span class="sxs-lookup"><span data-stu-id="5f2ba-106">Make sure that another process has not locked the file, and wait to open the file until the other process releases it.</span></span>  
  
3.  <span data-ttu-id="5f2ba-107">Per visualizzare il Registro di sistema, verificare che le autorizzazioni utente includano questo tipo di accesso del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="5f2ba-107">To access the registry, check that your user permissions include this type of registry access.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f2ba-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5f2ba-108">See Also</span></span>  
 [<span data-ttu-id="5f2ba-109">Tipi di errore</span><span class="sxs-lookup"><span data-stu-id="5f2ba-109">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
