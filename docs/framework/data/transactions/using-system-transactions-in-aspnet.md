---
title: Uso di System.Transactions in ASP.NET
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1982c300-7ea6-4242-95ed-dc28ccfacac9
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c94cd0a6cdddc4b49a59d6420d2ec28864285aa8
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="using-systemtransactions-in-aspnet"></a><span data-ttu-id="aa41e-102">Uso di System.Transactions in ASP.NET</span><span class="sxs-lookup"><span data-stu-id="aa41e-102">Using System.Transactions in ASP.NET</span></span>
<span data-ttu-id="aa41e-103">Questo argomento descrive come usare correttamente <xref:System.Transactions> all'interno di un'applicazione [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="aa41e-103">This topic describes how you can successfully use <xref:System.Transactions> inside an [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] application.</span></span>  
  
## <a name="enable-distributedtransactionpermission-in-aspnet"></a><span data-ttu-id="aa41e-104">Abilitare DistributedTransactionPermission in ASP.NET</span><span class="sxs-lookup"><span data-stu-id="aa41e-104">Enable DistributedTransactionPermission in ASP.NET</span></span>  
 <span data-ttu-id="aa41e-105"><xref:System.Transactions> supporta i chiamanti parzialmente attendibili ed è contrassegnato con l'attributo APTCA ( **AllowPartiallyTrustedCallers** ).</span><span class="sxs-lookup"><span data-stu-id="aa41e-105"><xref:System.Transactions> supports partially trusted callers and is marked with the **AllowPartiallyTrustedCallers** attribute (APTCA).</span></span> <span data-ttu-id="aa41e-106">I livelli di attendibilità per <xref:System.Transactions> sono definiti in base ai tipi di risorse (come memoria di sistema, risorse a livello di processo condivise, risorse a livello di sistema e altre risorse) esposti da <xref:System.Transactions> e in base al livello di attendibilità necessario per accedere a queste risorse.</span><span class="sxs-lookup"><span data-stu-id="aa41e-106">The trust levels for <xref:System.Transactions> are defined based on the types of resources, (for example, system memory, shared process-wide resources, system-wide resources, and other resources), that <xref:System.Transactions> exposes and the level of trust that should be required to access those resources.</span></span> <span data-ttu-id="aa41e-107">In un ambiente parzialmente attendibile un assembly con attendibilità non totale può usare solo le transazioni all'interno del dominio applicazione (in questo caso l'unica risorsa protetta è la memoria di sistema), a meno che non ottenga l'autorizzazione <xref:System.Transactions.DistributedTransactionPermission>.</span><span class="sxs-lookup"><span data-stu-id="aa41e-107">In a partial-trust environment, a non-full trust assembly can only use transactions within the Application Domain (in this case, the only resource being protected is system memory), unless it is granted the <xref:System.Transactions.DistributedTransactionPermission>.</span></span>  
  
 <span data-ttu-id="aa41e-108">L'autorizzazione<xref:System.Transactions.DistributedTransactionPermission> viene richiesta ogni volta che viene eseguita l'escalation della gestione della transazione in modo che questa venga gestita da Microsoft Distributed Transaction Coordinator (MSDTC).</span><span class="sxs-lookup"><span data-stu-id="aa41e-108"><xref:System.Transactions.DistributedTransactionPermission> is demanded whenever transaction management is escalated to be managed by the Microsoft Distributed Transaction Coordinator (MSDTC).</span></span> <span data-ttu-id="aa41e-109">Questo tipo di scenario utilizza risorse a livello di processo e in particolare una risorsa globale, ovvero lo spazio riservato nel log di MSDTC.</span><span class="sxs-lookup"><span data-stu-id="aa41e-109">This kind of scenario utilizes process-wide resources and particularly a global resource, which is the reserved space in the MSDTC log.</span></span> <span data-ttu-id="aa41e-110">Un esempio di questo utilizzo è un front-end Web per un database o per un'applicazione che usa un database come parte dei servizi forniti.</span><span class="sxs-lookup"><span data-stu-id="aa41e-110">An example of this usage is a Web front-end to a database or an application that uses a database as part of the services it provides.</span></span>  
  
 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]<span data-ttu-id="aa41e-111"> include un set di livelli di attendibilità proprio, a cui associa un set specifico di autorizzazioni tramite file dei criteri.</span><span class="sxs-lookup"><span data-stu-id="aa41e-111"> has its own set of trust levels and associates a specific set of permissions with these trust levels through policy files.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="aa41e-112">[File dei criteri e i livelli di attendibilità ASP.NET](http://msdn.microsoft.com/library/f897c794-10d3-414c-86b7-59b66564bbf1).</span><span class="sxs-lookup"><span data-stu-id="aa41e-112"> [ASP.NET Trust Levels and Policy Files](http://msdn.microsoft.com/library/f897c794-10d3-414c-86b7-59b66564bbf1).</span></span> <span data-ttu-id="aa41e-113">Quando si installa inizialmente Windows SDK, nessuno dei file dei criteri predefiniti di [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] è associato a <xref:System.Transactions.DistributedTransactionPermission>.</span><span class="sxs-lookup"><span data-stu-id="aa41e-113">When you initially install the Windows SDK, none of the default [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] policy files are associated with the <xref:System.Transactions.DistributedTransactionPermission>.</span></span> <span data-ttu-id="aa41e-114">Di conseguenza, quando viene eseguita l'escalation di una transazione appartenente a un'applicazione [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] in modo che venga gestita tramite MSDTC, l'escalation non riesce e viene generata un'eccezione <xref:System.Security.SecurityException> perché la transazione non ha l'autorizzazione <xref:System.Transactions.DistributedTransactionPermission>.</span><span class="sxs-lookup"><span data-stu-id="aa41e-114">As such, when your transaction in an [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] application is escalated to be managed by the MSDTC, the escalation fails with a <xref:System.Security.SecurityException> upon demanding the <xref:System.Transactions.DistributedTransactionPermission>.</span></span> <span data-ttu-id="aa41e-115">Per abilitare l'escalation delle transazioni in un ambiente [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] parzialmente attendibile, è necessario concedere l'autorizzazione <xref:System.Transactions.DistributedTransactionPermission> agli stessi livelli di attendibilità predefiniti indicati nell'autorizzazione <xref:System.Data.SqlClient.SqlClientPermission>.</span><span class="sxs-lookup"><span data-stu-id="aa41e-115">To enable transaction escalation in an [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] partial trust environment, you should grant the <xref:System.Transactions.DistributedTransactionPermission> in the same default trust levels as those of <xref:System.Data.SqlClient.SqlClientPermission>.</span></span> <span data-ttu-id="aa41e-116">A questo scopo, è possibile configurare un livello di attendibilità e un file dei criteri personalizzati oppure modificare i file dei criteri predefiniti, ovvero **Web_hightrust.config** e **Web_mediumtrust.config**.</span><span class="sxs-lookup"><span data-stu-id="aa41e-116">You can either configure your own custom trust level and policy file to support this, or you can modify the default policy files, which are **Web_hightrust.config** and **Web_mediumtrust.config**.</span></span>  
  
 <span data-ttu-id="aa41e-117">Per modificare i file dei criteri, aggiungere un **SecurityClass** elemento per **DistributedTransactionPermission** per il **SecurityClasses** elemento sotto il  **PolicyLevel** elemento e aggiungere un corrispondente **IPermission** elemento sotto il [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] **NamedPermissionSet** per System. Transactions.</span><span class="sxs-lookup"><span data-stu-id="aa41e-117">To modify the policy files, add a **SecurityClass** element for **DistributedTransactionPermission** to the **SecurityClasses** element under the **PolicyLevel** element and add a corresponding **IPermission** element under the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] **NamedPermissionSet** for System.Transactions.</span></span> <span data-ttu-id="aa41e-118">Queste modifiche vengono mostrate nel file di configurazione seguente.</span><span class="sxs-lookup"><span data-stu-id="aa41e-118">The following configuration file demonstrates this.</span></span>  
  
```xml  
<SecurityClasses>  
   <SecurityClass Name="DistributedTransactionPermission" Description="System.Transactions.DistributedTransactionPermission, System.Transactions, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>  
...  
</SecurityClasses>  
  
<PermissionSet  
  class="NamedPermissionSet"  
  version="1"  
  Name="ASP.Net">  
     <IPermission  
        class="System.Transactions.DistributedTransactionPermission, System.Transactions, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
        version="1"  
        Unrestricted="true"  
     />  
...  
</PermissionSet>  
```  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="aa41e-119">[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] criteri di sicurezza, vedere [elemento securityPolicy (Schema delle impostazioni ASP.NET)](http://msdn.microsoft.com/library/469d8d22-d263-46bb-8400-40d8d027faba).</span><span class="sxs-lookup"><span data-stu-id="aa41e-119"> [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] security policy, see [securityPolicy Element (ASP.NET Settings Schema)](http://msdn.microsoft.com/library/469d8d22-d263-46bb-8400-40d8d027faba).</span></span>  
  
## <a name="dynamic-compilation"></a><span data-ttu-id="aa41e-120">Compilazione dinamica</span><span class="sxs-lookup"><span data-stu-id="aa41e-120">Dynamic Compilation</span></span>  
 <span data-ttu-id="aa41e-121">Se si vuole importare e usare <xref:System.Transactions> in un'applicazione [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] compilata dinamicamente all'accesso, è necessario inserire nel file di configurazione un riferimento all'assembly <xref:System.Transactions> .</span><span class="sxs-lookup"><span data-stu-id="aa41e-121">If you want to import and use <xref:System.Transactions> in an [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] application that is dynamically compiled on access, you should place a reference to the <xref:System.Transactions> assembly in the configuration file.</span></span> <span data-ttu-id="aa41e-122">In particolare, il riferimento deve essere aggiunto nella sezione **compilation**/**assemblies** del file di configurazione **Web.config** radice predefinito oppure nel file di configurazione di un'applicazione Web specifica.</span><span class="sxs-lookup"><span data-stu-id="aa41e-122">Specifically, the reference should be added under the **compilation**/**assemblies** section of the default root **Web.config** configuration file, or a specific Web application's configuration file.</span></span> <span data-ttu-id="aa41e-123">Nell'esempio che segue viene illustrato quanto descritto.</span><span class="sxs-lookup"><span data-stu-id="aa41e-123">The following example demonstrates this.</span></span>  
  
```xml  
<configuration>  
   <system.web>  
      <compilation>  
         <assemblies>  
      <add assembly="System.Transactions, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
         </assemblies>  
      </compilation>  
   </system.web>  
</configuration>  
```  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="aa41e-124">[elemento add per assembly per la compilazione (Schema delle impostazioni ASP.NET)](http://msdn.microsoft.com/library/602197e8-108d-4249-b752-ba2a318f75e4).</span><span class="sxs-lookup"><span data-stu-id="aa41e-124"> [add Element for assemblies for compilation (ASP.NET Settings Schema)](http://msdn.microsoft.com/library/602197e8-108d-4249-b752-ba2a318f75e4).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa41e-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aa41e-125">See Also</span></span>  
 [<span data-ttu-id="aa41e-126">File dei criteri e i livelli di attendibilità di ASP.NET</span><span class="sxs-lookup"><span data-stu-id="aa41e-126">ASP.NET Trust Levels and Policy Files</span></span>](http://msdn.microsoft.com/library/f897c794-10d3-414c-86b7-59b66564bbf1)  
 [<span data-ttu-id="aa41e-127">Elemento securityPolicy (Schema delle impostazioni ASP.NET)</span><span class="sxs-lookup"><span data-stu-id="aa41e-127">securityPolicy Element (ASP.NET Settings Schema)</span></span>](http://msdn.microsoft.com/library/469d8d22-d263-46bb-8400-40d8d027faba)  
 [<span data-ttu-id="aa41e-128">Escalation della gestione delle transazioni</span><span class="sxs-lookup"><span data-stu-id="aa41e-128">Transaction Management Escalation</span></span>](../../../../docs/framework/data/transactions/transaction-management-escalation.md)
