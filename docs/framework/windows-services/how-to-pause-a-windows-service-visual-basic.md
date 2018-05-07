---
title: 'Procedura: sospendere un servizio Windows (Visual Basic)'
ms.date: 03/30/2017
dev_langs:
- vb
f1_keywords:
- ServiceController.Pause
helpviewer_keywords:
- Windows Service applications, pausing
- pausing Windows Service applications
ms.assetid: eddb9409-942b-46b6-a2ce-fbd4c65f2790
author: ghogen
manager: douge
ms.openlocfilehash: 43a852f1b618582c5aa65636e0a529434f8fd6a1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-pause-a-windows-service-visual-basic"></a>Procedura: sospendere un servizio Windows (Visual Basic)
Questo esempio viene utilizzato il <xref:System.ServiceProcess.ServiceController> componente per sospendere il servizio di amministrazione di IIS nel computer locale.  
  
## <a name="example"></a>Esempio  
 [!code-vb[VbRadconService#11](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#11)]  
[!code-vb[VbRadconService#12](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#12)]  
  
 Questo esempio di codice è disponibile anche come frammento di codice IntelliSense. In selezione frammento di codice, si trova in **sistema operativo Windows > Windows Services**. Per altre informazioni, vedere [Code Snippets](/visualstudio/ide/code-snippets) (Frammenti di codice).  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Un riferimento progetto a System.serviceprocess.dll.  
  
-   Accedere ai membri dello spazio dei nomi <xref:System.ServiceProcess>. Aggiungere un'istruzione `Imports` se i nomi dei membri all'interno del codice non sono specificati in modo completo. Per altre informazioni, vedere [Istruzione Imports (tipo e spazio dei nomi .NET)](~/docs/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Il <xref:System.ServiceProcess.ServiceController.MachineName%2A> proprietà la <xref:System.ServiceProcess.ServiceController> classe è il computer locale per impostazione predefinita. Per fare riferimento a servizi di Windows in un altro computer, modificare il <xref:System.ServiceProcess.ServiceController.MachineName%2A> proprietà sul nome del computer.  
  
 Le seguenti condizioni possono generare un'eccezione:  
  
-   Il servizio non può essere sospeso. (<xref:System.InvalidOperationException>)  
  
-   Si è verificato un errore durante l'accesso a un'API di sistema. (<xref:System.ComponentModel.Win32Exception>)  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 Il controllo dei servizi del computer può essere limitato tramite la <xref:System.ServiceProcess.ServiceControllerPermissionAccess> come impostare le autorizzazioni di <xref:System.ServiceProcess.ServiceControllerPermission>.  
  
 Utilizzando, è possibile limitare l'accesso alle informazioni sul servizio di <xref:System.Security.Permissions.PermissionState> come impostare le autorizzazioni di <xref:System.Security.Permissions.SecurityPermission>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceProcess.ServiceController>  
 <xref:System.ServiceProcess.ServiceControllerStatus>  
 <xref:System.ServiceProcess.ServiceController.WaitForStatus%2A>  
 [Procedura: continuare un servizio Windows (Visual Basic)](../../../docs/framework/windows-services/how-to-continue-a-windows-service-visual-basic.md)
