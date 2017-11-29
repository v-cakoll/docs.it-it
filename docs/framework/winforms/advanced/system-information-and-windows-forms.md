---
title: Informazioni sul sistema e Windows Form
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- domain names [Windows Forms], retrieving
- SystemInformation class [Windows Forms]
- user names [Windows Forms], retrieving
- system information [Windows Forms]
ms.assetid: 30cf43a3-8cb2-4ff3-862b-6c34576616a8
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6657556ffb49c19e6ffc3ef5462de341a93112b8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="system-information-and-windows-forms"></a><span data-ttu-id="c1f0a-102">Informazioni sul sistema e Windows Form</span><span class="sxs-lookup"><span data-stu-id="c1f0a-102">System Information and Windows Forms</span></span>
<span data-ttu-id="c1f0a-103">Talvolta è necessario raccogliere informazioni sul computer in cui l'applicazione è in esecuzione su per prendere decisioni nel codice.</span><span class="sxs-lookup"><span data-stu-id="c1f0a-103">Sometimes it is necessary to gather information about the computer that your application is running on in order to make decisions in your code.</span></span> <span data-ttu-id="c1f0a-104">Ad esempio, potrebbe essere una funzione che è disponibile solo quando si è connessi a un dominio di rete specifica. In questo caso, è necessario un modo per determinare il dominio e disabilitare la funzione se il dominio non è presentano.</span><span class="sxs-lookup"><span data-stu-id="c1f0a-104">For example, you might have a function that is only applicable when connected to a particular network domain; in this case you would need a way to determine the domain and disable the function if the domain is not present.</span></span>  
  
 <span data-ttu-id="c1f0a-105">Applicazioni Windows Form è possono utilizzare la <xref:System.Windows.Forms.SystemInformation> classe per determinare un numero di operazioni per il computer in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="c1f0a-105">Windows Forms applications can use the <xref:System.Windows.Forms.SystemInformation> class to determine a number of things about a computer at run time.</span></span> <span data-ttu-id="c1f0a-106">Nell'esempio seguente viene illustrato l'utilizzo di <xref:System.Windows.Forms.SystemInformation> classe per recuperare il <xref:System.Windows.Forms.SystemInformation.UserName%2A> e <xref:System.Windows.Forms.SystemInformation.UserDomainName%2A>:</span><span class="sxs-lookup"><span data-stu-id="c1f0a-106">The following example demonstrates using the <xref:System.Windows.Forms.SystemInformation> class to retrieve the <xref:System.Windows.Forms.SystemInformation.UserName%2A> and <xref:System.Windows.Forms.SystemInformation.UserDomainName%2A>:</span></span>  
  
```vb  
Dim User As String = Windows.Forms.SystemInformation.UserName  
Dim Domain As String = Windows.Forms.SystemInformation.UserDomainName  
  
MessageBox.Show("Good morning " & User & ". You are connected to " _  
& Domain)  
```  
  
```csharp  
string User = SystemInformation.UserName;  
string Domain = SystemInformation.UserDomainName;  
  
MessageBox.Show("Good morning " + User + ". You are connected to " _  
+ Domain)  
```  
  
 <span data-ttu-id="c1f0a-107">Tutti i membri del <xref:System.Windows.Forms.SystemInformation> classe sono di sola lettura; non è possibile modificare le impostazioni dell'utente.</span><span class="sxs-lookup"><span data-stu-id="c1f0a-107">All members of the <xref:System.Windows.Forms.SystemInformation> class are read-only; you cannot modify a user's settings.</span></span> <span data-ttu-id="c1f0a-108">Sono presenti più di 100 membri della classe, la restituzione di informazioni su tutti gli elementi dal numero di monitor collegati al computer (<xref:System.Windows.Forms.SystemInformation.MonitorCount%2A>) per la spaziatura tra le icone in Esplora risorse (<xref:System.Windows.Forms.SystemInformation.IconHorizontalSpacing%2A> e <xref:System.Windows.Forms.SystemInformation.IconVerticalSpacing%2A>).</span><span class="sxs-lookup"><span data-stu-id="c1f0a-108">There are over 100 members of the class, returning information on everything from the number of monitors attached to the computer (<xref:System.Windows.Forms.SystemInformation.MonitorCount%2A>) to the spacing of icons in Windows Explorer (<xref:System.Windows.Forms.SystemInformation.IconHorizontalSpacing%2A> and <xref:System.Windows.Forms.SystemInformation.IconVerticalSpacing%2A>).</span></span>  
  
 <span data-ttu-id="c1f0a-109">Alcuni dei membri di più utili di <xref:System.Windows.Forms.SystemInformation> classe includono <xref:System.Windows.Forms.SystemInformation.ComputerName%2A>, <xref:System.Windows.Forms.SystemInformation.DbcsEnabled%2A>, <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>, e <xref:System.Windows.Forms.SystemInformation.TerminalServerSession%2A>.</span><span class="sxs-lookup"><span data-stu-id="c1f0a-109">Some of the more useful members of the <xref:System.Windows.Forms.SystemInformation> class include <xref:System.Windows.Forms.SystemInformation.ComputerName%2A>, <xref:System.Windows.Forms.SystemInformation.DbcsEnabled%2A>, <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>, and <xref:System.Windows.Forms.SystemInformation.TerminalServerSession%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1f0a-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c1f0a-110">See Also</span></span>  
 <xref:System.Windows.Forms.SystemInformation>  
 [<span data-ttu-id="c1f0a-111">Risparmio energia in Windows Form</span><span class="sxs-lookup"><span data-stu-id="c1f0a-111">Power Management in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/power-management-in-windows-forms.md)
