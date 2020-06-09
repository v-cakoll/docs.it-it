---
title: Autorizzazione dell'accesso alle operazioni del servizio
ms.date: 03/30/2017
helpviewer_keywords:
- service behaviors, authorizing access sample
- Authorizing Access To Service Operations Sample [Windows Communication Foundation]
- authorization, Windows Communication Foundation sample
ms.assetid: ddcfdaa5-8b2e-4e13-bd85-887209dc6328
ms.openlocfilehash: 3097c86f50a75dec8a649ca4e1edd2511a046ca8
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84585532"
---
# <a name="authorizing-access-to-service-operations"></a>Autorizzazione dell'accesso alle operazioni del servizio
In questo esempio viene illustrato come utilizzare [\<serviceAuthorization>](../../configure-apps/file-schema/wcf/serviceauthorization-element.md) per consentire l'utilizzo dell' <xref:System.Security.Permissions.PrincipalPermissionAttribute> attributo per autorizzare l'accesso alle operazioni del servizio. Questo esempio è basato sull'esempio [Introduzione](getting-started-sample.md) . Il servizio e il client sono configurati utilizzando [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) . L' `mode` attributo di [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) è stato impostato su `Message` e `clientCredentialType` è stato impostato su `Windows` . <xref:System.Security.Permissions.PrincipalPermissionAttribute> viene applicato a ogni metodo del servizio e usato per limitare l'accesso alle operazioni. Il chiamante deve essere un amministratore Windows per accedere a tutte le operazioni.  
  
 In questo esempio, il client è un'applicazione console (.exe) e il servizio è ospitato da Internet Information Services (IIS).  
  
> [!NOTE]
> La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
 Il file di configurazione del servizio usa [\<serviceAuthorization>](../../configure-apps/file-schema/wcf/serviceauthorization-element.md) per impostare l' `principalPermissionMode` attributo:  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior>
      <!-- The serviceAuthorization behavior sets the  
           principalPermissionMode to UseWindowsGroups.  
           This puts a WindowsPrincipal on the current thread when a   
           service is invoked. -->  
      <serviceAuthorization principalPermissionMode="UseWindowsGroups" />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 L'impostazione della `principalPermissionMode` su `UseWindowsGroups` abilita l'uso di <xref:System.Security.Permissions.PrincipalPermissionAttribute> basato sui nomi dei gruppi di Windows.  
  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute> viene applicato a ogni operazione per richiedere che il chiamante appartenga al gruppo Administrators di Windows, come illustrato nell'esempio di codice seguente.  
  
```csharp
[PrincipalPermission(SecurityAction.Demand,
                             Role = "Builtin\\Administrators")]  
public double Add(double n1, double n2)  
{  
    double result = n1 + n2;  
    return result;  
}  
```  
  
 Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client. Il client comunica correttamente con ogni operazione se viene eseguito con un account che appartiene al gruppo Administrators. In caso contrario, l'accesso viene negato. Per sperimentare un errore di autorizzazione, eseguire il client con un account che non appartiene al gruppo Administrators. Premere INVIO nella finestra della console per arrestare il client.  
  
 Un servizio può ricevere una notifica di errori di autorizzazione implementando un <xref:System.ServiceModel.Dispatcher.IErrorHandler>. Per informazioni sull'implementazione di, vedere [estensione del controllo sulla gestione degli errori e creazione di report](extending-control-over-error-handling-and-reporting.md) `IErrorHandler` .  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1. Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md).  
  
3. Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).  
