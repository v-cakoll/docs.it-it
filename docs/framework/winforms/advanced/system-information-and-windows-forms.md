---
title: Informazioni sul sistema e Windows Form
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
ms.openlocfilehash: d8efb783fcb5bcbe9c4ee99bc784e27a1aebb0cf
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57707664"
---
# <a name="system-information-and-windows-forms"></a>Informazioni sul sistema e Windows Form
In alcuni casi è necessario raccogliere informazioni sui computer in cui l'applicazione è in esecuzione su per prendere decisioni nel codice. Ad esempio, potrebbe essere una funzione che è disponibile solo quando si è connessi a un dominio di rete specifica. In questo caso, è necessario un modo per determinare il dominio e se non è presente il dominio, disabilitare la funzione.  
  
 Le applicazioni Windows Forms è possono usare il <xref:System.Windows.Forms.SystemInformation> classe per determinare una serie di operazioni su un computer in fase di esecuzione. Nell'esempio seguente viene illustrato come utilizzare il <xref:System.Windows.Forms.SystemInformation> classe da cui recuperare il <xref:System.Windows.Forms.SystemInformation.UserName%2A> e <xref:System.Windows.Forms.SystemInformation.UserDomainName%2A>:  
  
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
  
 Tutti i membri del <xref:System.Windows.Forms.SystemInformation> classe sono di sola lettura; non è possibile modificare le impostazioni dell'utente. Sono presenti più di 100 membri della classe, la restituzione di informazioni su tutti gli elementi dal numero di monitor connessi al computer (<xref:System.Windows.Forms.SystemInformation.MonitorCount%2A>) per la spaziatura tra le icone in Windows Explorer (<xref:System.Windows.Forms.SystemInformation.IconHorizontalSpacing%2A> e <xref:System.Windows.Forms.SystemInformation.IconVerticalSpacing%2A>).  
  
 Alcuni dei membri di più utili la <xref:System.Windows.Forms.SystemInformation> classe includono <xref:System.Windows.Forms.SystemInformation.ComputerName%2A>, <xref:System.Windows.Forms.SystemInformation.DbcsEnabled%2A>, <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>, e <xref:System.Windows.Forms.SystemInformation.TerminalServerSession%2A>.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.SystemInformation>
- [Risparmio energia in Windows Form](power-management-in-windows-forms.md)
