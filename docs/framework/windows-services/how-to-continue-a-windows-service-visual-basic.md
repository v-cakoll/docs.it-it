---
title: 'Procedura: Continuare un servizio Windows (Visual Basic)'
description: Informazioni su come usare il componente ServiceController per continuare un servizio Windows, ad esempio il servizio di amministrazione di IIS, in un computer locale con Visual Basic.
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
ms.openlocfilehash: 2a04e330ea7dc37552053b2a7915909c011727f8
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925787"
---
# <a name="how-to-continue-a-windows-service-visual-basic"></a>Procedura: Continuare un servizio Windows (Visual Basic)
Questo esempio usa il componente <xref:System.ServiceProcess.ServiceController> per continuare l'esecuzione del servizio IIS Admin nel computer locale.  
  
## <a name="example"></a>Esempio  
 [!code-vb[VbRadconService#11](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#11)]  
[!code-vb[VbRadconService#13](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#13)]  
  
 Questo esempio di codice è disponibile anche come frammento di codice IntelliSense. Nello strumento di selezione dei frammenti di codice il frammento si trova in **Sistema operativo Windows > Servizi Windows**. Per altre informazioni, vedere [Code Snippets](/visualstudio/ide/code-snippets) (Frammenti di codice).  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Un riferimento del progetto a System.serviceprocess.dll.  
  
- Accedere ai membri dello spazio dei nomi <xref:System.ServiceProcess>. Aggiungere un'istruzione `Imports` se i nomi dei membri all'interno del codice non sono specificati in modo completo. Per altre informazioni, vedere [Istruzione Imports (tipo e spazio dei nomi .NET)](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 La proprietà <xref:System.ServiceProcess.ServiceController.MachineName%2A> della classe <xref:System.ServiceProcess.ServiceController> è il computer locale per impostazione predefinita. Per fare riferimento a servizi di Windows in un altro computer, modificare la proprietà <xref:System.ServiceProcess.ServiceController.MachineName%2A> impostando il nome di tale computer.  
  
 Non è possibile chiamare il metodo <xref:System.ServiceProcess.ServiceController.Continue%2A> su un servizio fino a quando lo stato del controller del servizio è <xref:System.ServiceProcess.ServiceControllerStatus.Paused>.  
  
 Le seguenti condizioni possono generare un'eccezione:  
  
- Non è possibile riprendere il servizio. (<xref:System.InvalidOperationException>)  
  
- Si è verificato un errore durante l'accesso a un'API di sistema. (<xref:System.ComponentModel.Win32Exception>)  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 Il controllo dei servizi nel computer può essere limitato tramite l'enumerazione <xref:System.ServiceProcess.ServiceControllerPermissionAccess> per impostare le autorizzazioni nella classe <xref:System.ServiceProcess.ServiceControllerPermission>.  
  
 L'accesso alle informazioni sul servizio può essere limitato tramite l'enumerazione <xref:System.Security.Permissions.PermissionState> per impostare le autorizzazioni nella classe <xref:System.Security.Permissions.SecurityPermission>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceProcess.ServiceController>
- <xref:System.ServiceProcess.ServiceControllerStatus>
- [Procedura: Sospendere un servizio Windows (Visual Basic)](how-to-pause-a-windows-service-visual-basic.md)
