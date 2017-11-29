---
title: 'Procedura: avviare un''applicazione e inviarle sequenze di tasti (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- keystrokes, sending
- Shell command example [Visual Basic]
- processes, starting and sending keystrokes
- SendKeys.SendWait examples
ms.assetid: f1303184-fce4-44fb-88b4-aac5f42d5d77
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8bf92a74bc1b60ea3213d80e4df373936c65d89e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-start-an-application-and-send-it-keystrokes-visual-basic"></a><span data-ttu-id="c3394-102">Procedura: avviare un'applicazione e inviarle sequenze di tasti (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c3394-102">How to: Start an Application and Send it Keystrokes (Visual Basic)</span></span>
<span data-ttu-id="c3394-103">In questo esempio viene usata la funzione `Shell` per avviare l'applicazione Calcolatrice e vengono moltiplicati due numeri tramite l'invio di sequenze di tasti con il metodo `My.Computer.Keyboard.SendKeys`.</span><span class="sxs-lookup"><span data-stu-id="c3394-103">This example uses the `Shell` function to start the calculator application and then multiplies two numbers by sending keystrokes using the `My.Computer.Keyboard.SendKeys` method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c3394-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="c3394-104">Example</span></span>  
 [!code-vb[VbVbalrMyComputer#25](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-start-an-application-and-send-it-keystrokes_1.vb)]  
  
## <a name="robust-programming"></a><span data-ttu-id="c3394-105">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="c3394-105">Robust Programming</span></span>  
 <span data-ttu-id="c3394-106">Se non viene rilevata un'applicazione con l'identificatore di processo richiesto, viene generata un'eccezione <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="c3394-106">A <xref:System.ArgumentException> exception is raised if an application with the requested process identifier cannot be found.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="c3394-107">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c3394-107">.NET Framework Security</span></span>  
 <span data-ttu-id="c3394-108">La chiamata alla funzione `Shell` richiede l'attendibilità totale (classe <xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="c3394-108">The call to the `Shell` function requires full trust (<xref:System.Security.SecurityException> class).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3394-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c3394-109">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Devices.Keyboard.SendKeys%2A>  
 <xref:Microsoft.VisualBasic.Interaction.Shell%2A>  
 <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>
