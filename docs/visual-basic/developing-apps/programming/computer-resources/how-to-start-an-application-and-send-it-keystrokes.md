---
title: "Procedura: avviare un'applicazione e inviarle sequenze di tasti Visual Basic"
ms.date: 10/23/2019
helpviewer_keywords:
- keystrokes, sending
- Shell command example [Visual Basic]
- processes, starting and sending keystrokes
- SendKeys.SendWait examples
ms.assetid: f1303184-fce4-44fb-88b4-aac5f42d5d77
ms.openlocfilehash: 033999c07bb5839a264122b2ca330916bdf844b8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "72919396"
---
# <a name="how-to-start-an-application-and-send-it-keystrokes-visual-basic"></a><span data-ttu-id="c0219-102">Procedura: avviare un'applicazione e inviarle sequenze di tasti (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c0219-102">How to: start an application and send it keystrokes (Visual Basic)</span></span>

<span data-ttu-id="c0219-103">In questo esempio viene <xref:Microsoft.VisualBasic.Interaction.Shell%2A> utilizzato il metodo per avviare l'applicazione blocco note e quindi viene stampata una frase inviando sequenze di tasti utilizzando il metodo [My. computer. Keyboard. SendKeys](xref:Microsoft.VisualBasic.Devices.Keyboard.SendKeys%2A) .</span><span class="sxs-lookup"><span data-stu-id="c0219-103">This example uses the <xref:Microsoft.VisualBasic.Interaction.Shell%2A> method to start the Notepad application and then prints a sentence by sending keystrokes using the [My.Computer.Keyboard.SendKeys](xref:Microsoft.VisualBasic.Devices.Keyboard.SendKeys%2A) method.</span></span>

## <a name="example"></a><span data-ttu-id="c0219-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="c0219-104">Example</span></span>

[!code-vb[VbVbalrMyComputer#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#25)]

## <a name="robust-programming"></a><span data-ttu-id="c0219-105">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="c0219-105">Robust programming</span></span>

<span data-ttu-id="c0219-106">Se <xref:System.ArgumentException> non è possibile trovare un'applicazione con l'identificatore di processo richiesto, viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="c0219-106">An <xref:System.ArgumentException> exception is raised if an application with the requested process identifier cannot be found.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="c0219-107">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c0219-107">.NET Framework Security</span></span>

<span data-ttu-id="c0219-108">La chiamata alla funzione `Shell` richiede l'attendibilità totale (classe <xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="c0219-108">The call to the `Shell` function requires full trust (<xref:System.Security.SecurityException> class).</span></span>

## <a name="see-also"></a><span data-ttu-id="c0219-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c0219-109">See also</span></span>

- <xref:Microsoft.VisualBasic.Devices.Keyboard.SendKeys%2A>
- <xref:Microsoft.VisualBasic.Interaction.Shell%2A>
- <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>
