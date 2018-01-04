---
title: 'Procedura: limitare l''accesso tramite la classe PrincipalPermissionAttribute'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PrincipalPermissionAttribute class
- WCF, authorization
- WCF, security
ms.assetid: 5162f5c4-8781-4cc4-9425-bb7620eaeaf4
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: da91e3456fdca863980c89f45e0cc28db19170be
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-restrict-access-with-the-principalpermissionattribute-class"></a>Procedura: limitare l'accesso tramite la classe PrincipalPermissionAttribute
Il controllo dell'accesso alle risorse di un computer appartenente a un dominio Windows è un'attività di sicurezza di base. Ad esempio, solo determinati utenti devono essere in grado di visualizzare i dati riservati, ad esempio le informazioni sulle retribuzioni dei dipendenti. In questo argomento viene descritto come consentire l'accesso a un metodo specifico esclusivamente agli utenti che appartengono a un determinato gruppo. Per un esempio funzionante, vedere [autorizzare l'accesso alle operazioni del servizio](../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md).  
  
 Questa attività è costituita da due procedure distinte. La prima crea il gruppo e lo popola di utenti, mentre la seconda applica la classe <xref:System.Security.Permissions.PrincipalPermissionAttribute> per definire il gruppo.  
  
### <a name="to-create-a-windows-group"></a>Per creare un gruppo di Windows  
  
1.  Aprire il **Gestione Computer** console.  
  
2.  Nel riquadro sinistro, fare clic su **utenti e gruppi locali**.  
  
3.  Fare doppio clic su **gruppi**, fare clic su **nuovo gruppo**.  
  
4.  Nel **nome gruppo** , digitare un nome per il nuovo gruppo.  
  
5.  Nel **descrizione** , digitare una descrizione del nuovo gruppo.  
  
6.  Fare clic su di **Aggiungi** pulsante per aggiungere nuovi membri al gruppo.  
  
7.  Gli utenti che si aggiungono al gruppo e desiderano testare il codice seguente devono disconnettersi dal computer e quindi connettersi nuovamente per essere inclusi effettivamente nel gruppo.  
  
### <a name="to-demand-user-membership"></a>Per richiedere l'appartenenza dell'utente  
  
1.  Aprire il file di codice di [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] contenente il codice del contratto di servizio implementato. [!INCLUDE[crabout](../../../includes/crabout-md.md)]implementazione di un contratto, vedere [contratti di servizio che implementa](../../../docs/framework/wcf/implementing-service-contracts.md).  
  
2.  Applicare l'attributo <xref:System.Security.Permissions.PrincipalPermissionAttribute> a ogni metodo per cui si desidera che l'accesso sia consentito esclusivamente a un gruppo specifico. Impostare la proprietà <xref:System.Security.Permissions.SecurityAttribute.Action%2A> su <xref:System.Security.Permissions.SecurityAction.Demand> e la proprietà <xref:System.Security.Permissions.PrincipalPermissionAttribute.Role%2A> sul nome del gruppo. Ad esempio:  
  
     [!code-csharp[c_PrincipalPermissionAttribute#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_principalpermissionattribute/cs/source.cs#1)]
     [!code-vb[c_PrincipalPermissionAttribute#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_principalpermissionattribute/vb/source.vb#1)]  
  
    > [!NOTE]
    >  Se si applica l'attributo <xref:System.Security.Permissions.PrincipalPermissionAttribute> ad un contratto, verrà generata la classe <xref:System.Security.SecurityException>. È possibile applicare l'attributo soltanto a livello di metodo.  
  
## <a name="using-a-certificate-to-control-access-to-a-method"></a>Utilizzo di un certificato per controllare l'accesso a un metodo  
 Se il tipo di credenziale client è un certificato, l'accesso a un metodo può anche essere controllato mediante la classe `PrincipalPermissionAttribute`. A tale scopo è necessario disporre del soggetto e dell'identificazione personale del certificato.  
  
 Per esaminare un certificato per le proprietà, vedere [procedura: visualizzare certificati con lo Snap-in MMC](../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md). Per trovare il valore di identificazione personale, vedere [procedura: recuperare l'identificazione personale del certificato](../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).  
  
#### <a name="to-control-access-using-a-certificate"></a>Per controllare l'accesso tramite un certificato  
  
1.  Applicare la classe <xref:System.Security.Permissions.PrincipalPermissionAttribute> al metodo per cui si desidera limitare l'accesso.  
  
2.  Impostare l'azione dell'attributo su <xref:System.Security.Permissions.SecurityAction.Demand?displayProperty=nameWithType>.  
  
3.  Impostare la proprietà `Name` su una stringa costituita dal nome del soggetto e dall'identificazione personale del certificato. Separare i due valori con un punto e virgola e un spazio, come mostrato nell'esempio seguente:  
  
     [!code-csharp[c_PrincipalPermissionAttribute#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_principalpermissionattribute/cs/source.cs#2)]
     [!code-vb[c_PrincipalPermissionAttribute#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_principalpermissionattribute/vb/source.vb#2)]  
  
4.  Impostare la proprietà <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> su <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles> come illustrato nell'esempio di configurazione seguente:  
  
    ```xml  
    <behaviors>  
      <serviceBehaviors>  
      <behavior name="SvcBehavior1">  
      <serviceAuthorization principalPermissionMode="UseAspNetRoles" />  
      </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    ```  
  
     L'impostazione di questo valore su `UseAspNetRoles` indica che la proprietà `Name` dell'elemento `PrincipalPermissionAttribute` viene utilizzata per eseguire un confronto tra stringhe. Per impostazione predefinita, quando un certificato viene utilizzato come credenziale client, [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] concatena il nome comune e l'identificazione personale del certificato con un punto e virgola allo scopo di creare un valore univoco da utilizzare come identità primaria del client. Se nel servizio la modalità `UseAspNetRoles` è stata impostata su `PrincipalPermissionMode`, questo valore di identità primaria viene confrontato con il valore della proprietà `Name` per determinare i diritti di accesso dell'utente.  
  
     In alternativa, quando si crea un servizio indipendente, impostare la proprietà <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> in codice, come mostrato nel codice seguente:  
  
     [!code-csharp[c_PrincipalPermissionAttribute#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_principalpermissionattribute/cs/source.cs#3)]
     [!code-vb[c_PrincipalPermissionAttribute#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_principalpermissionattribute/vb/source.vb#3)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
 <xref:System.Security.Permissions.SecurityAction.Demand>  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute.Role%2A>  
 [Autorizzazione dell'accesso alle operazioni del servizio](../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)  
 [Panoramica della sicurezza](../../../docs/framework/wcf/feature-details/security-overview.md)  
 [Implementazione dei contratti di servizio](../../../docs/framework/wcf/implementing-service-contracts.md)
