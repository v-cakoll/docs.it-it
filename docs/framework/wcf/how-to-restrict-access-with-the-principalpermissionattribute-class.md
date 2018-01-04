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
# <a name="how-to-restrict-access-with-the-principalpermissionattribute-class"></a><span data-ttu-id="bd8a4-102">Procedura: limitare l'accesso tramite la classe PrincipalPermissionAttribute</span><span class="sxs-lookup"><span data-stu-id="bd8a4-102">How to: Restrict Access with the PrincipalPermissionAttribute Class</span></span>
<span data-ttu-id="bd8a4-103">Il controllo dell'accesso alle risorse di un computer appartenente a un dominio Windows è un'attività di sicurezza di base.</span><span class="sxs-lookup"><span data-stu-id="bd8a4-103">Controlling the access to resources on a Windows-domain computer is a basic security task.</span></span> <span data-ttu-id="bd8a4-104">Ad esempio, solo determinati utenti devono essere in grado di visualizzare i dati riservati, ad esempio le informazioni sulle retribuzioni dei dipendenti.</span><span class="sxs-lookup"><span data-stu-id="bd8a4-104">For example, only certain users should be able to view sensitive data, such as payroll information.</span></span> <span data-ttu-id="bd8a4-105">In questo argomento viene descritto come consentire l'accesso a un metodo specifico esclusivamente agli utenti che appartengono a un determinato gruppo.</span><span class="sxs-lookup"><span data-stu-id="bd8a4-105">This topic explains how to restrict access to a method by demanding that the user belong to a predefined group.</span></span> <span data-ttu-id="bd8a4-106">Per un esempio funzionante, vedere [autorizzare l'accesso alle operazioni del servizio](../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md).</span><span class="sxs-lookup"><span data-stu-id="bd8a4-106">For a working sample, see [Authorizing Access to Service Operations](../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md).</span></span>  
  
 <span data-ttu-id="bd8a4-107">Questa attività è costituita da due procedure distinte.</span><span class="sxs-lookup"><span data-stu-id="bd8a4-107">The task consists of two separate procedures.</span></span> <span data-ttu-id="bd8a4-108">La prima crea il gruppo e lo popola di utenti,</span><span class="sxs-lookup"><span data-stu-id="bd8a4-108">The first creates the group and populates it with users.</span></span> <span data-ttu-id="bd8a4-109">mentre la seconda applica la classe <xref:System.Security.Permissions.PrincipalPermissionAttribute> per definire il gruppo.</span><span class="sxs-lookup"><span data-stu-id="bd8a4-109">The second applies the <xref:System.Security.Permissions.PrincipalPermissionAttribute> class to specify the group.</span></span>  
  
### <a name="to-create-a-windows-group"></a><span data-ttu-id="bd8a4-110">Per creare un gruppo di Windows</span><span class="sxs-lookup"><span data-stu-id="bd8a4-110">To create a Windows group</span></span>  
  
1.  <span data-ttu-id="bd8a4-111">Aprire il **Gestione Computer** console.</span><span class="sxs-lookup"><span data-stu-id="bd8a4-111">Open the **Computer Management** console.</span></span>  
  
2.  <span data-ttu-id="bd8a4-112">Nel riquadro sinistro, fare clic su **utenti e gruppi locali**.</span><span class="sxs-lookup"><span data-stu-id="bd8a4-112">In the left panel, click **Local Users and Groups**.</span></span>  
  
3.  <span data-ttu-id="bd8a4-113">Fare doppio clic su **gruppi**, fare clic su **nuovo gruppo**.</span><span class="sxs-lookup"><span data-stu-id="bd8a4-113">Right-click **Groups**, and click **New Group**.</span></span>  
  
4.  <span data-ttu-id="bd8a4-114">Nel **nome gruppo** , digitare un nome per il nuovo gruppo.</span><span class="sxs-lookup"><span data-stu-id="bd8a4-114">In the **Group Name** box, type a name for the new group.</span></span>  
  
5.  <span data-ttu-id="bd8a4-115">Nel **descrizione** , digitare una descrizione del nuovo gruppo.</span><span class="sxs-lookup"><span data-stu-id="bd8a4-115">In the **Description** box, type a description of the new group.</span></span>  
  
6.  <span data-ttu-id="bd8a4-116">Fare clic su di **Aggiungi** pulsante per aggiungere nuovi membri al gruppo.</span><span class="sxs-lookup"><span data-stu-id="bd8a4-116">Click the **Add** button to add new members to the group.</span></span>  
  
7.  <span data-ttu-id="bd8a4-117">Gli utenti che si aggiungono al gruppo e desiderano testare il codice seguente devono disconnettersi dal computer e quindi connettersi nuovamente per essere inclusi effettivamente nel gruppo.</span><span class="sxs-lookup"><span data-stu-id="bd8a4-117">If you have added yourself to the group and want to test the following code, you must log off the computer and log back on to be included in the group.</span></span>  
  
### <a name="to-demand-user-membership"></a><span data-ttu-id="bd8a4-118">Per richiedere l'appartenenza dell'utente</span><span class="sxs-lookup"><span data-stu-id="bd8a4-118">To demand user membership</span></span>  
  
1.  <span data-ttu-id="bd8a4-119">Aprire il file di codice di [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] contenente il codice del contratto di servizio implementato.</span><span class="sxs-lookup"><span data-stu-id="bd8a4-119">Open the [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] code file that contains the implemented service contract code.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="bd8a4-120">implementazione di un contratto, vedere [contratti di servizio che implementa](../../../docs/framework/wcf/implementing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="bd8a4-120"> implementing a contract, see [Implementing Service Contracts](../../../docs/framework/wcf/implementing-service-contracts.md).</span></span>  
  
2.  <span data-ttu-id="bd8a4-121">Applicare l'attributo <xref:System.Security.Permissions.PrincipalPermissionAttribute> a ogni metodo per cui si desidera che l'accesso sia consentito esclusivamente a un gruppo specifico.</span><span class="sxs-lookup"><span data-stu-id="bd8a4-121">Apply the <xref:System.Security.Permissions.PrincipalPermissionAttribute> attribute to each method that must be restricted to a specific group.</span></span> <span data-ttu-id="bd8a4-122">Impostare la proprietà <xref:System.Security.Permissions.SecurityAttribute.Action%2A> su <xref:System.Security.Permissions.SecurityAction.Demand> e la proprietà <xref:System.Security.Permissions.PrincipalPermissionAttribute.Role%2A> sul nome del gruppo.</span><span class="sxs-lookup"><span data-stu-id="bd8a4-122">Set the <xref:System.Security.Permissions.SecurityAttribute.Action%2A> property to <xref:System.Security.Permissions.SecurityAction.Demand> and the <xref:System.Security.Permissions.PrincipalPermissionAttribute.Role%2A> property to the name of the group.</span></span> <span data-ttu-id="bd8a4-123">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="bd8a4-123">For example:</span></span>  
  
     [!code-csharp[c_PrincipalPermissionAttribute#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_principalpermissionattribute/cs/source.cs#1)]
     [!code-vb[c_PrincipalPermissionAttribute#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_principalpermissionattribute/vb/source.vb#1)]  
  
    > [!NOTE]
    >  <span data-ttu-id="bd8a4-124">Se si applica l'attributo <xref:System.Security.Permissions.PrincipalPermissionAttribute> ad un contratto, verrà generata la classe <xref:System.Security.SecurityException>.</span><span class="sxs-lookup"><span data-stu-id="bd8a4-124">If you apply the <xref:System.Security.Permissions.PrincipalPermissionAttribute> attribute to a contract a <xref:System.Security.SecurityException> will be thrown.</span></span> <span data-ttu-id="bd8a4-125">È possibile applicare l'attributo soltanto a livello di metodo.</span><span class="sxs-lookup"><span data-stu-id="bd8a4-125">You can only apply the attribute at the method level.</span></span>  
  
## <a name="using-a-certificate-to-control-access-to-a-method"></a><span data-ttu-id="bd8a4-126">Utilizzo di un certificato per controllare l'accesso a un metodo</span><span class="sxs-lookup"><span data-stu-id="bd8a4-126">Using a Certificate to Control Access to a Method</span></span>  
 <span data-ttu-id="bd8a4-127">Se il tipo di credenziale client è un certificato, l'accesso a un metodo può anche essere controllato mediante la classe `PrincipalPermissionAttribute`.</span><span class="sxs-lookup"><span data-stu-id="bd8a4-127">You can also use the `PrincipalPermissionAttribute` class to control access to a method if the client credential type is a certificate.</span></span> <span data-ttu-id="bd8a4-128">A tale scopo è necessario disporre del soggetto e dell'identificazione personale del certificato.</span><span class="sxs-lookup"><span data-stu-id="bd8a4-128">To do this, you must have the certificate's subject and thumbprint.</span></span>  
  
 <span data-ttu-id="bd8a4-129">Per esaminare un certificato per le proprietà, vedere [procedura: visualizzare certificati con lo Snap-in MMC](../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).</span><span class="sxs-lookup"><span data-stu-id="bd8a4-129">To examine a certificate for its properties, see [How to: View Certificates with the MMC Snap-in](../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).</span></span> <span data-ttu-id="bd8a4-130">Per trovare il valore di identificazione personale, vedere [procedura: recuperare l'identificazione personale del certificato](../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="bd8a4-130">To find the thumbprint value, see [How to: Retrieve the Thumbprint of a Certificate](../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span></span>  
  
#### <a name="to-control-access-using-a-certificate"></a><span data-ttu-id="bd8a4-131">Per controllare l'accesso tramite un certificato</span><span class="sxs-lookup"><span data-stu-id="bd8a4-131">To control access using a certificate</span></span>  
  
1.  <span data-ttu-id="bd8a4-132">Applicare la classe <xref:System.Security.Permissions.PrincipalPermissionAttribute> al metodo per cui si desidera limitare l'accesso.</span><span class="sxs-lookup"><span data-stu-id="bd8a4-132">Apply the <xref:System.Security.Permissions.PrincipalPermissionAttribute> class to the method you want to restrict access to.</span></span>  
  
2.  <span data-ttu-id="bd8a4-133">Impostare l'azione dell'attributo su <xref:System.Security.Permissions.SecurityAction.Demand?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bd8a4-133">Set the action of the attribute to <xref:System.Security.Permissions.SecurityAction.Demand?displayProperty=nameWithType>.</span></span>  
  
3.  <span data-ttu-id="bd8a4-134">Impostare la proprietà `Name` su una stringa costituita dal nome del soggetto e dall'identificazione personale del certificato.</span><span class="sxs-lookup"><span data-stu-id="bd8a4-134">Set the `Name` property to a string that consists of the subject name and the certificate's thumbprint.</span></span> <span data-ttu-id="bd8a4-135">Separare i due valori con un punto e virgola e un spazio, come mostrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="bd8a4-135">Separate the two values with a semicolon and a space, as shown in the following example:</span></span>  
  
     [!code-csharp[c_PrincipalPermissionAttribute#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_principalpermissionattribute/cs/source.cs#2)]
     [!code-vb[c_PrincipalPermissionAttribute#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_principalpermissionattribute/vb/source.vb#2)]  
  
4.  <span data-ttu-id="bd8a4-136">Impostare la proprietà <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> su <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles> come illustrato nell'esempio di configurazione seguente:</span><span class="sxs-lookup"><span data-stu-id="bd8a4-136">Set the <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> property to <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles> as shown in the following configuration example:</span></span>  
  
    ```xml  
    <behaviors>  
      <serviceBehaviors>  
      <behavior name="SvcBehavior1">  
      <serviceAuthorization principalPermissionMode="UseAspNetRoles" />  
      </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    ```  
  
     <span data-ttu-id="bd8a4-137">L'impostazione di questo valore su `UseAspNetRoles` indica che la proprietà `Name` dell'elemento `PrincipalPermissionAttribute` viene utilizzata per eseguire un confronto tra stringhe.</span><span class="sxs-lookup"><span data-stu-id="bd8a4-137">Setting this value to `UseAspNetRoles` indicates that the `Name` property of the `PrincipalPermissionAttribute` will be used to perform a string comparison.</span></span> <span data-ttu-id="bd8a4-138">Per impostazione predefinita, quando un certificato viene utilizzato come credenziale client, [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] concatena il nome comune e l'identificazione personale del certificato con un punto e virgola allo scopo di creare un valore univoco da utilizzare come identità primaria del client.</span><span class="sxs-lookup"><span data-stu-id="bd8a4-138">When a certificate is used as a client credential, by default [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] concatenates the certificate common name and the thumbprint with a semicolon to create a unique value for the client's primary identity.</span></span> <span data-ttu-id="bd8a4-139">Se nel servizio la modalità `UseAspNetRoles` è stata impostata su `PrincipalPermissionMode`, questo valore di identità primaria viene confrontato con il valore della proprietà `Name` per determinare i diritti di accesso dell'utente.</span><span class="sxs-lookup"><span data-stu-id="bd8a4-139">With `UseAspNetRoles` set as the `PrincipalPermissionMode` on the service, this primary identity value is compared with the `Name` property value to determine the access rights of the user.</span></span>  
  
     <span data-ttu-id="bd8a4-140">In alternativa, quando si crea un servizio indipendente, impostare la proprietà <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> in codice, come mostrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="bd8a4-140">Alternatively, when creating a self-hosted service, set the <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> property in code as shown in the following code:</span></span>  
  
     [!code-csharp[c_PrincipalPermissionAttribute#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_principalpermissionattribute/cs/source.cs#3)]
     [!code-vb[c_PrincipalPermissionAttribute#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_principalpermissionattribute/vb/source.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="bd8a4-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bd8a4-141">See Also</span></span>  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
 <xref:System.Security.Permissions.SecurityAction.Demand>  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute.Role%2A>  
 [<span data-ttu-id="bd8a4-142">Autorizzazione dell'accesso alle operazioni del servizio</span><span class="sxs-lookup"><span data-stu-id="bd8a4-142">Authorizing Access to Service Operations</span></span>](../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)  
 [<span data-ttu-id="bd8a4-143">Panoramica della sicurezza</span><span class="sxs-lookup"><span data-stu-id="bd8a4-143">Security Overview</span></span>](../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="bd8a4-144">Implementazione dei contratti di servizio</span><span class="sxs-lookup"><span data-stu-id="bd8a4-144">Implementing Service Contracts</span></span>](../../../docs/framework/wcf/implementing-service-contracts.md)
