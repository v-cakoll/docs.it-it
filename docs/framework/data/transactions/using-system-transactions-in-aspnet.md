---
title: Uso di System.Transactions in ASP.NET
ms.date: 03/30/2017
ms.assetid: 1982c300-7ea6-4242-95ed-dc28ccfacac9
ms.openlocfilehash: 2bddebc13897408839e18f42b17a9fbaefdc5b87
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040414"
---
# <a name="using-systemtransactions-in-aspnet"></a><span data-ttu-id="ccb09-102">Uso di System.Transactions in ASP.NET</span><span class="sxs-lookup"><span data-stu-id="ccb09-102">Using System.Transactions in ASP.NET</span></span>
<span data-ttu-id="ccb09-103">Questo argomento descrive il modo in cui è possibile utilizzare correttamente lo spazio dei nomi <xref:System.Transactions> all'interno di un'applicazione ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="ccb09-103">This topic describes how you can successfully use <xref:System.Transactions> inside an ASP.NET application.</span></span>

## <a name="enable-distributedtransactionpermission-in-aspnet"></a><span data-ttu-id="ccb09-104">Abilitare DistributedTransactionPermission in ASP.NET</span><span class="sxs-lookup"><span data-stu-id="ccb09-104">Enable DistributedTransactionPermission in ASP.NET</span></span>
 <span data-ttu-id="ccb09-105">Lo spazio dei nomi <xref:System.Transactions> supporta i chiamanti parzialmente attendibili ed è contrassegnato con l'attributo APTCA (`AllowPartiallyTrustedCallers`).</span><span class="sxs-lookup"><span data-stu-id="ccb09-105"><xref:System.Transactions> supports partially trusted callers and is marked with the `AllowPartiallyTrustedCallers` attribute (APTCA).</span></span> <span data-ttu-id="ccb09-106">I livelli di attendibilità per <xref:System.Transactions> vengono definiti in base ai tipi di risorse (ad esempio memoria di sistema, risorse a livello di processo condivise, risorse a livello di sistema e altre risorse) che <xref:System.Transactions> espone e il livello di attendibilità necessario per accedere a tali risorse risorse.</span><span class="sxs-lookup"><span data-stu-id="ccb09-106">The trust levels for <xref:System.Transactions> are defined based on the types of resources (for example, system memory, shared process-wide resources, system-wide resources, and other resources) that <xref:System.Transactions> exposes and the level of trust that should be required to access those resources.</span></span> <span data-ttu-id="ccb09-107">In un ambiente parzialmente attendibile un assembly con attendibilità non totale può usare solo le transazioni all'interno del dominio applicazione (in questo caso l'unica risorsa protetta è la memoria di sistema), a meno che non ottenga l'autorizzazione <xref:System.Transactions.DistributedTransactionPermission>.</span><span class="sxs-lookup"><span data-stu-id="ccb09-107">In a partial-trust environment, a non-full trust assembly can only use transactions within the Application Domain (in this case, the only resource being protected is system memory), unless it is granted the <xref:System.Transactions.DistributedTransactionPermission>.</span></span>

 <span data-ttu-id="ccb09-108">L'autorizzazione<xref:System.Transactions.DistributedTransactionPermission> viene richiesta ogni volta che viene eseguita l'escalation della gestione della transazione in modo che questa venga gestita da Microsoft Distributed Transaction Coordinator (MSDTC).</span><span class="sxs-lookup"><span data-stu-id="ccb09-108"><xref:System.Transactions.DistributedTransactionPermission> is demanded whenever transaction management is escalated to be managed by the Microsoft Distributed Transaction Coordinator (MSDTC).</span></span> <span data-ttu-id="ccb09-109">Questo tipo di scenario utilizza risorse a livello di processo e in particolare una risorsa globale, ovvero lo spazio riservato nel log di MSDTC.</span><span class="sxs-lookup"><span data-stu-id="ccb09-109">This kind of scenario utilizes process-wide resources and particularly a global resource, which is the reserved space in the MSDTC log.</span></span> <span data-ttu-id="ccb09-110">Un esempio di questo utilizzo è un front-end Web per un database o per un'applicazione che usa un database come parte dei servizi forniti.</span><span class="sxs-lookup"><span data-stu-id="ccb09-110">An example of this usage is a Web front-end to a database or an application that uses a database as part of the services it provides.</span></span>

 <span data-ttu-id="ccb09-111">ASP.NET dispone di un proprio set di livelli di attendibilità, a cui associa un set specifico di autorizzazioni utilizzando i file dei criteri.</span><span class="sxs-lookup"><span data-stu-id="ccb09-111">ASP.NET has its own set of trust levels and associates a specific set of permissions with these trust levels through policy files.</span></span> <span data-ttu-id="ccb09-112">Per altre informazioni, vedere [ASP.NET Trust Levels and Policy Files](https://docs.microsoft.com/previous-versions/aspnet/wyts434y(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="ccb09-112">For more information, see [ASP.NET Trust Levels and Policy Files](https://docs.microsoft.com/previous-versions/aspnet/wyts434y(v=vs.100)).</span></span> <span data-ttu-id="ccb09-113">Quando si installa inizialmente il Windows SDK, nessuno dei file dei criteri ASP.NET predefiniti è associato al <xref:System.Transactions.DistributedTransactionPermission>.</span><span class="sxs-lookup"><span data-stu-id="ccb09-113">When you initially install the Windows SDK, none of the default ASP.NET policy files are associated with the <xref:System.Transactions.DistributedTransactionPermission>.</span></span> <span data-ttu-id="ccb09-114">Ne consegue che quando si tenta di eseguire l'escalation di una transazione appartenente a un'applicazione ASP.NET in modo che venga gestita tramite MSDTC, tale tentativo ha esito negativo e viene generata un'eccezione <xref:System.Security.SecurityException> in quanto la transazione non dispone dell'autorizzazione <xref:System.Transactions.DistributedTransactionPermission>.</span><span class="sxs-lookup"><span data-stu-id="ccb09-114">As such, when your transaction in an ASP.NET application is escalated to be managed by the MSDTC, the escalation fails with a <xref:System.Security.SecurityException> upon demanding the <xref:System.Transactions.DistributedTransactionPermission>.</span></span> <span data-ttu-id="ccb09-115">Per abilitare l'escalation delle transazioni in un ambiente ASP.NET parzialmente attendibile, è necessario concedere l'autorizzazione <xref:System.Transactions.DistributedTransactionPermission> agli stessi livelli di attendibilità predefiniti indicati nell'autorizzazione <xref:System.Data.SqlClient.SqlClientPermission>.</span><span class="sxs-lookup"><span data-stu-id="ccb09-115">To enable transaction escalation in an ASP.NET partial trust environment, you should grant the <xref:System.Transactions.DistributedTransactionPermission> in the same default trust levels as those of <xref:System.Data.SqlClient.SqlClientPermission>.</span></span> <span data-ttu-id="ccb09-116">A questo scopo, è possibile configurare un livello di attendibilità e un file dei criteri personalizzati oppure modificare i file dei criteri predefiniti, ovvero **Web_hightrust.config** e **Web_mediumtrust.config**.</span><span class="sxs-lookup"><span data-stu-id="ccb09-116">You can either configure your own custom trust level and policy file to support this, or you can modify the default policy files, which are **Web_hightrust.config** and **Web_mediumtrust.config**.</span></span>

 <span data-ttu-id="ccb09-117">Per modificare i file dei criteri, aggiungere un elemento `SecurityClass` dell'autorizzazione `DistributedTransactionPermission` all'elemento `SecurityClasses` all'interno dell'elemento `PolicyLevel`. Quindi, aggiungere un elemento `IPermission` corrispondente all'interno della raccolta `NamedPermissionSet` di ASP.NET di System.Transactions.</span><span class="sxs-lookup"><span data-stu-id="ccb09-117">To modify the policy files, add a `SecurityClass` element for `DistributedTransactionPermission` to the `SecurityClasses` element under the `PolicyLevel` element and add a corresponding `IPermission` element under the ASP.NET `NamedPermissionSet` for System.Transactions.</span></span> <span data-ttu-id="ccb09-118">Queste modifiche vengono mostrate nel file di configurazione seguente.</span><span class="sxs-lookup"><span data-stu-id="ccb09-118">The following configuration file demonstrates this.</span></span>

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

 <span data-ttu-id="ccb09-119">Per ulteriori informazioni sui criteri di sicurezza di ASP.NET, vedere [elemento securityPolicy (schema delle impostazioni ASP.NET)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/zhs35b56(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="ccb09-119">For more information about ASP.NET security policy, see [securityPolicy Element (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/zhs35b56(v=vs.100)).</span></span>

## <a name="dynamic-compilation"></a><span data-ttu-id="ccb09-120">Compilazione dinamica</span><span class="sxs-lookup"><span data-stu-id="ccb09-120">Dynamic Compilation</span></span>
 <span data-ttu-id="ccb09-121">Se si desidera importare e utilizzare lo spazio dei nomi <xref:System.Transactions> in un'applicazione ASP.NET compilata dinamicamente all'accesso, è necessario inserire nel file di configurazione un riferimento all'assembly <xref:System.Transactions>.</span><span class="sxs-lookup"><span data-stu-id="ccb09-121">If you want to import and use <xref:System.Transactions> in an ASP.NET application that is dynamically compiled on access, you should place a reference to the <xref:System.Transactions> assembly in the configuration file.</span></span> <span data-ttu-id="ccb09-122">In particolare, il riferimento deve essere aggiunto nella sezione `compilation/assemblies` del file di configurazione **Web. config** radice predefinito oppure in un file di configurazione di un'applicazione Web specifica.</span><span class="sxs-lookup"><span data-stu-id="ccb09-122">Specifically, the reference should be added under the `compilation/assemblies` section of the default root **Web.config** configuration file, or a specific Web application's configuration file.</span></span> <span data-ttu-id="ccb09-123">Nell'esempio che segue viene illustrato quanto descritto.</span><span class="sxs-lookup"><span data-stu-id="ccb09-123">The following example demonstrates this.</span></span>

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

 <span data-ttu-id="ccb09-124">Per ulteriori informazioni, vedere [elemento Add per gli assembly per la compilazione (schema delle impostazioni ASP.NET)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/37e2zyhb(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="ccb09-124">For more information, see [add Element for assemblies for compilation (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/37e2zyhb(v=vs.100)).</span></span>

## <a name="see-also"></a><span data-ttu-id="ccb09-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ccb09-125">See also</span></span>

- <span data-ttu-id="ccb09-126">[Livelli di attendibilità ASP.NET e file di criteri](https://docs.microsoft.com/previous-versions/aspnet/wyts434y(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="ccb09-126">[ASP.NET Trust Levels and Policy Files](https://docs.microsoft.com/previous-versions/aspnet/wyts434y(v=vs.100))</span></span>
- <span data-ttu-id="ccb09-127">[Elemento securityPolicy (schema delle impostazioni ASP.NET)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/zhs35b56(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="ccb09-127">[securityPolicy Element (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/zhs35b56(v=vs.100))</span></span>
- [<span data-ttu-id="ccb09-128">Escalation della gestione delle transazioni</span><span class="sxs-lookup"><span data-stu-id="ccb09-128">Transaction Management Escalation</span></span>](transaction-management-escalation.md)
