---
title: 'Procedura: continuare un servizio Windows (Visual Basic)'
ms.date: 03/30/2017
dev_langs:
- vb
f1_keywords:
- ServiceController.Continue
helpviewer_keywords:
- Windows Service applications, pausing
- pausing Windows Service applications
ms.assetid: e5d13760-4c83-4b0d-abef-39852677cd7a
author: ghogen
manager: douge
ms.openlocfilehash: 15ef15e0afe43d56db0972a686cd093e22c672dc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-continue-a-windows-service-visual-basic"></a>Procedura: continuare un servizio Windows (Visual Basic)
Questo esempio viene utilizzato il <xref:System.ServiceProcess.ServiceController> componente di riprendere il servizio di amministrazione di IIS nel computer locale.  
  
## <a name="example"></a>Esempio  
 [!code-vb[VbRadconService#11](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#11)]  
[!code-vb[VbRadconService#13](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#13)]  
  
 Questo esempio di codice è disponibile anche come frammento di codice IntelliSense. In selezione frammento di codice, si trova in **sistema operativo Windows > Windows Services**. Per altre informazioni, vedere [Code Snippets](/visualstudio/ide/code-snippets) (Frammenti di codice).  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Un riferimento progetto a System.serviceprocess.dll.  
  
-   Accedere ai membri dello spazio dei nomi <xref:System.ServiceProcess>. Aggiungere un'istruzione `Imports` se i nomi dei membri all'interno del codice non sono specificati in modo completo. Per altre informazioni, vedere [Istruzione Imports (tipo e spazio dei nomi .NET)](~/docs/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Il <xref:System.ServiceProcess.ServiceController.MachineName%2A> proprietà la <xref:System.ServiceProcess.ServiceController> classe è il computer locale per impostazione predefinita. Per fare riferimento a servizi di Windows in un altro computer, modificare il <xref:System.ServiceProcess.ServiceController.MachineName%2A> proprietà sul nome del computer.  
  
 Non è possibile chiamare il <xref:System.ServiceProcess.ServiceController.Continue%2A> metodo su un servizio fino a quando lo stato del servizio controller è <xref:System.ServiceProcess.ServiceControllerStatus.Paused>.  
  
 Le seguenti condizioni possono generare un'eccezione:  
  
-   Impossibile riprendere il servizio. (<xref:System.InvalidOperationException>)  
  
-   Si è verificato un errore durante l'accesso a un'API di sistema. (<xref:System.ComponentModel.Win32Exception>)  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 Il controllo dei servizi del computer può essere limitato tramite la <xref:System.ServiceProcess.ServiceControllerPermissionAccess> enumerazione come impostare le autorizzazioni di <xref:System.ServiceProcess.ServiceControllerPermission> classe.  
  
 Utilizzando, è possibile limitare l'accesso alle informazioni sul servizio di <xref:System.Security.Permissions.PermissionState> enumerazione come impostare le autorizzazioni di <xref:System.Security.Permissions.SecurityPermission> classe.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceProcess.ServiceController>  
 <xref:System.ServiceProcess.ServiceControllerStatus>  
 [Procedura: sospendere un servizio Windows (Visual Basic)](../../../docs/framework/windows-services/how-to-pause-a-windows-service-visual-basic.md)
