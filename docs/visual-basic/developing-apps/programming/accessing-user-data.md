---
title: Accesso ai dati utente (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- domain names [Visual Basic], retrieving
- data [Visual Basic], accessing user data
- My.User object [Visual Basic], tasks
- user data [Visual Basic], domain
- user names [Visual Basic], retrieving
- user data [Visual Basic], accessing
- login names [Visual Basic]
- examples [Visual Basic], accessing user data
ms.assetid: 32492a15-ee59-4a63-a1f1-9b24cc13140a
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 92c0b97059896e86d54069b637c9956cac9d10e8
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="accessing-user-data-visual-basic"></a><span data-ttu-id="fde67-102">Accesso ai dati utente (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fde67-102">Accessing User Data (Visual Basic)</span></span>
<span data-ttu-id="fde67-103">Questa sezione contiene argomenti relativi all'oggetto `My.User` e alle attività che tale oggetto consente di eseguire.</span><span class="sxs-lookup"><span data-stu-id="fde67-103">This section contains topics dealing with the `My.User` object and tasks that you can accomplish with it.</span></span>  
  
 <span data-ttu-id="fde67-104">L'oggetto `My.User` consente di accedere alle informazioni sull'utente connesso restituendo un oggetto in grado di implementare l'interfaccia <xref:System.Security.Principal.IPrincipal>.</span><span class="sxs-lookup"><span data-stu-id="fde67-104">The `My.User` object provides access to information about the logged-on user by returning an object that implements the <xref:System.Security.Principal.IPrincipal> interface.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="fde67-105">Attività</span><span class="sxs-lookup"><span data-stu-id="fde67-105">Tasks</span></span>  
  
|<span data-ttu-id="fde67-106">Per</span><span class="sxs-lookup"><span data-stu-id="fde67-106">To</span></span>|<span data-ttu-id="fde67-107">Vedere</span><span class="sxs-lookup"><span data-stu-id="fde67-107">See</span></span>|  
|--------|---------|  
|<span data-ttu-id="fde67-108">Ottenere il nome dell'account di accesso dell'utente</span><span class="sxs-lookup"><span data-stu-id="fde67-108">Get the user's login name</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.User.Name%2A>|  
|<span data-ttu-id="fde67-109">Ottenere il nome di dominio dell'utente se l'applicazione usa l'autenticazione di Windows</span><span class="sxs-lookup"><span data-stu-id="fde67-109">Get the user's domain name, if the application uses Windows authentication</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.User.CurrentPrincipal>|  
|<span data-ttu-id="fde67-110">Determinare il ruolo dell'utente</span><span class="sxs-lookup"><span data-stu-id="fde67-110">Determine the user's role</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.User.IsInRole%2A>|  
  
## <a name="see-also"></a><span data-ttu-id="fde67-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fde67-111">See Also</span></span>  
 <xref:Microsoft.VisualBasic.ApplicationServices.User>
