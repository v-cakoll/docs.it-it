---
title: Accesso ai dati utente (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: 097006caf56072d5a6e9f2945f5969eed249849e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33582844"
---
# <a name="accessing-user-data-visual-basic"></a><span data-ttu-id="caa00-102">Accesso ai dati utente (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="caa00-102">Accessing User Data (Visual Basic)</span></span>
<span data-ttu-id="caa00-103">Questa sezione contiene argomenti relativi all'oggetto `My.User` e alle attività che tale oggetto consente di eseguire.</span><span class="sxs-lookup"><span data-stu-id="caa00-103">This section contains topics dealing with the `My.User` object and tasks that you can accomplish with it.</span></span>  
  
 <span data-ttu-id="caa00-104">L'oggetto `My.User` consente di accedere alle informazioni sull'utente connesso restituendo un oggetto in grado di implementare l'interfaccia <xref:System.Security.Principal.IPrincipal>.</span><span class="sxs-lookup"><span data-stu-id="caa00-104">The `My.User` object provides access to information about the logged-on user by returning an object that implements the <xref:System.Security.Principal.IPrincipal> interface.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="caa00-105">Attività</span><span class="sxs-lookup"><span data-stu-id="caa00-105">Tasks</span></span>  
  
|<span data-ttu-id="caa00-106">A</span><span class="sxs-lookup"><span data-stu-id="caa00-106">To</span></span>|<span data-ttu-id="caa00-107">Vedere</span><span class="sxs-lookup"><span data-stu-id="caa00-107">See</span></span>|  
|--------|---------|  
|<span data-ttu-id="caa00-108">Ottenere il nome dell'account di accesso dell'utente</span><span class="sxs-lookup"><span data-stu-id="caa00-108">Get the user's login name</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.User.Name%2A>|  
|<span data-ttu-id="caa00-109">Ottenere il nome di dominio dell'utente se l'applicazione usa l'autenticazione di Windows</span><span class="sxs-lookup"><span data-stu-id="caa00-109">Get the user's domain name, if the application uses Windows authentication</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.User.CurrentPrincipal>|  
|<span data-ttu-id="caa00-110">Determinare il ruolo dell'utente</span><span class="sxs-lookup"><span data-stu-id="caa00-110">Determine the user's role</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.User.IsInRole%2A>|  
  
## <a name="see-also"></a><span data-ttu-id="caa00-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="caa00-111">See Also</span></span>  
 <xref:Microsoft.VisualBasic.ApplicationServices.User>
