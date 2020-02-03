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
# <a name="system-information-and-windows-forms"></a>Informazioni sul sistema e Windows Form
A volte è necessario raccogliere informazioni sul computer in cui è in esecuzione l'applicazione per prendere decisioni nel codice. Ad esempio, si potrebbe avere una funzione applicabile solo quando si è connessi a un particolare dominio di rete; in questo caso è necessario un modo per determinare il dominio e disabilitare la funzione se il dominio non è presente.  
  
 Windows Forms applicazioni possono utilizzare la classe <xref:System.Windows.Forms.SystemInformation> per determinare una serie di elementi relativi a un computer in fase di esecuzione. Nell'esempio seguente viene illustrato l'utilizzo della classe <xref:System.Windows.Forms.SystemInformation> per recuperare i <xref:System.Windows.Forms.SystemInformation.UserName%2A> e <xref:System.Windows.Forms.SystemInformation.UserDomainName%2A>:  
  
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
  
 Tutti i membri della classe <xref:System.Windows.Forms.SystemInformation> sono di sola lettura. non è possibile modificare le impostazioni di un utente. Sono presenti più di 100 membri della classe, che restituiscono informazioni su qualsiasi elemento, dal numero di monitoraggi collegati al computer (<xref:System.Windows.Forms.SystemInformation.MonitorCount%2A>) alla spaziatura delle icone in Esplora risorse (<xref:System.Windows.Forms.SystemInformation.IconHorizontalSpacing%2A> e <xref:System.Windows.Forms.SystemInformation.IconVerticalSpacing%2A>).  
  
 Alcuni dei membri più utili della classe <xref:System.Windows.Forms.SystemInformation> includono <xref:System.Windows.Forms.SystemInformation.ComputerName%2A>, <xref:System.Windows.Forms.SystemInformation.DbcsEnabled%2A>, <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>e <xref:System.Windows.Forms.SystemInformation.TerminalServerSession%2A>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.SystemInformation>
- [Risparmio energia in Windows Form](power-management-in-windows-forms.md)
