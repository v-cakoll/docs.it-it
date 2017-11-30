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
# <a name="system-information-and-windows-forms"></a>Informazioni sul sistema e Windows Form
Talvolta è necessario raccogliere informazioni sul computer in cui l'applicazione è in esecuzione su per prendere decisioni nel codice. Ad esempio, potrebbe essere una funzione che è disponibile solo quando si è connessi a un dominio di rete specifica. In questo caso, è necessario un modo per determinare il dominio e disabilitare la funzione se il dominio non è presentano.  
  
 Applicazioni Windows Form è possono utilizzare la <xref:System.Windows.Forms.SystemInformation> classe per determinare un numero di operazioni per il computer in fase di esecuzione. Nell'esempio seguente viene illustrato l'utilizzo di <xref:System.Windows.Forms.SystemInformation> classe per recuperare il <xref:System.Windows.Forms.SystemInformation.UserName%2A> e <xref:System.Windows.Forms.SystemInformation.UserDomainName%2A>:  
  
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
  
 Tutti i membri del <xref:System.Windows.Forms.SystemInformation> classe sono di sola lettura; non è possibile modificare le impostazioni dell'utente. Sono presenti più di 100 membri della classe, la restituzione di informazioni su tutti gli elementi dal numero di monitor collegati al computer (<xref:System.Windows.Forms.SystemInformation.MonitorCount%2A>) per la spaziatura tra le icone in Esplora risorse (<xref:System.Windows.Forms.SystemInformation.IconHorizontalSpacing%2A> e <xref:System.Windows.Forms.SystemInformation.IconVerticalSpacing%2A>).  
  
 Alcuni dei membri di più utili di <xref:System.Windows.Forms.SystemInformation> classe includono <xref:System.Windows.Forms.SystemInformation.ComputerName%2A>, <xref:System.Windows.Forms.SystemInformation.DbcsEnabled%2A>, <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>, e <xref:System.Windows.Forms.SystemInformation.TerminalServerSession%2A>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.SystemInformation>  
 [Risparmio energia in Windows Form](../../../../docs/framework/winforms/advanced/power-management-in-windows-forms.md)
