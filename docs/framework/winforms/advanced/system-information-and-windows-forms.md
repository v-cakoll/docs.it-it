---
title: Informazioni di sistema
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- domain names [Windows Forms], retrieving
- SystemInformation class [Windows Forms]
- user names [Windows Forms], retrieving
- system information [Windows Forms]
ms.assetid: 30cf43a3-8cb2-4ff3-862b-6c34576616a8
ms.openlocfilehash: a91e2fd8db0ef338ce30f89f11869f1b6698af3b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732582"
---
# <a name="system-information-and-windows-forms"></a><span data-ttu-id="7801b-102">Informazioni sul sistema e Windows Form</span><span class="sxs-lookup"><span data-stu-id="7801b-102">System Information and Windows Forms</span></span>
<span data-ttu-id="7801b-103">A volte è necessario raccogliere informazioni sul computer in cui è in esecuzione l'applicazione per prendere decisioni nel codice.</span><span class="sxs-lookup"><span data-stu-id="7801b-103">Sometimes it is necessary to gather information about the computer that your application is running on in order to make decisions in your code.</span></span> <span data-ttu-id="7801b-104">Ad esempio, si potrebbe avere una funzione applicabile solo quando si è connessi a un particolare dominio di rete; in questo caso è necessario un modo per determinare il dominio e disabilitare la funzione se il dominio non è presente.</span><span class="sxs-lookup"><span data-stu-id="7801b-104">For example, you might have a function that is only applicable when connected to a particular network domain; in this case you would need a way to determine the domain and disable the function if the domain is not present.</span></span>  
  
 <span data-ttu-id="7801b-105">Windows Forms applicazioni possono utilizzare la classe <xref:System.Windows.Forms.SystemInformation> per determinare una serie di elementi relativi a un computer in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="7801b-105">Windows Forms applications can use the <xref:System.Windows.Forms.SystemInformation> class to determine a number of things about a computer at run time.</span></span> <span data-ttu-id="7801b-106">Nell'esempio seguente viene illustrato l'utilizzo della classe <xref:System.Windows.Forms.SystemInformation> per recuperare i <xref:System.Windows.Forms.SystemInformation.UserName%2A> e <xref:System.Windows.Forms.SystemInformation.UserDomainName%2A>:</span><span class="sxs-lookup"><span data-stu-id="7801b-106">The following example demonstrates using the <xref:System.Windows.Forms.SystemInformation> class to retrieve the <xref:System.Windows.Forms.SystemInformation.UserName%2A> and <xref:System.Windows.Forms.SystemInformation.UserDomainName%2A>:</span></span>  
  
```vb  
Dim User As String = Windows.Forms.SystemInformation.UserName  
Dim Domain As String = Windows.Forms.SystemInformation.UserDomainName  
  
MessageBox.Show("Good morning " & User & ". You are connected to " _  
& Domain)  
```  
  
```csharp  
string User = SystemInformation.UserName;  
string Domain = SystemInformation.UserDomainName;  
  
MessageBox.Show("Good morning " + User + ". You are connected to "
+ Domain);
```  
  
 <span data-ttu-id="7801b-107">Tutti i membri della classe <xref:System.Windows.Forms.SystemInformation> sono di sola lettura. non è possibile modificare le impostazioni di un utente.</span><span class="sxs-lookup"><span data-stu-id="7801b-107">All members of the <xref:System.Windows.Forms.SystemInformation> class are read-only; you cannot modify a user's settings.</span></span> <span data-ttu-id="7801b-108">Sono presenti più di 100 membri della classe, che restituiscono informazioni su qualsiasi elemento, dal numero di monitoraggi collegati al computer (<xref:System.Windows.Forms.SystemInformation.MonitorCount%2A>) alla spaziatura delle icone in Esplora risorse (<xref:System.Windows.Forms.SystemInformation.IconHorizontalSpacing%2A> e <xref:System.Windows.Forms.SystemInformation.IconVerticalSpacing%2A>).</span><span class="sxs-lookup"><span data-stu-id="7801b-108">There are over 100 members of the class, returning information on everything from the number of monitors attached to the computer (<xref:System.Windows.Forms.SystemInformation.MonitorCount%2A>) to the spacing of icons in Windows Explorer (<xref:System.Windows.Forms.SystemInformation.IconHorizontalSpacing%2A> and <xref:System.Windows.Forms.SystemInformation.IconVerticalSpacing%2A>).</span></span>  
  
 <span data-ttu-id="7801b-109">Alcuni dei membri più utili della classe <xref:System.Windows.Forms.SystemInformation> includono <xref:System.Windows.Forms.SystemInformation.ComputerName%2A>, <xref:System.Windows.Forms.SystemInformation.DbcsEnabled%2A>, <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>e <xref:System.Windows.Forms.SystemInformation.TerminalServerSession%2A>.</span><span class="sxs-lookup"><span data-stu-id="7801b-109">Some of the more useful members of the <xref:System.Windows.Forms.SystemInformation> class include <xref:System.Windows.Forms.SystemInformation.ComputerName%2A>, <xref:System.Windows.Forms.SystemInformation.DbcsEnabled%2A>, <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>, and <xref:System.Windows.Forms.SystemInformation.TerminalServerSession%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7801b-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7801b-110">See also</span></span>

- <xref:System.Windows.Forms.SystemInformation>
- [<span data-ttu-id="7801b-111">Risparmio energia in Windows Form</span><span class="sxs-lookup"><span data-stu-id="7801b-111">Power Management in Windows Forms</span></span>](power-management-in-windows-forms.md)
