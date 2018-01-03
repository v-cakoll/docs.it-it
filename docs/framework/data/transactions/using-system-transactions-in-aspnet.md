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
ms.openlocfilehash: caa0f8cc5b98ae50e1c9d2da716dd03eb5cb4565
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="using-systemtransactions-in-aspnet"></a>Uso di System.Transactions in ASP.NET
Questo argomento descrive come usare correttamente <xref:System.Transactions> all'interno di un'applicazione [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] .  
  
## <a name="enable-distributedtransactionpermission-in-aspnet"></a>Abilitare DistributedTransactionPermission in ASP.NET  
 <xref:System.Transactions> supporta i chiamanti parzialmente attendibili ed è contrassegnato con l'attributo APTCA ( **AllowPartiallyTrustedCallers** ). I livelli di attendibilità per <xref:System.Transactions> sono definiti in base ai tipi di risorse (come memoria di sistema, risorse a livello di processo condivise, risorse a livello di sistema e altre risorse) esposti da <xref:System.Transactions> e in base al livello di attendibilità necessario per accedere a queste risorse. In un ambiente parzialmente attendibile un assembly con attendibilità non totale può usare solo le transazioni all'interno del dominio applicazione (in questo caso l'unica risorsa protetta è la memoria di sistema), a meno che non ottenga l'autorizzazione <xref:System.Transactions.DistributedTransactionPermission>.  
  
 L'autorizzazione<xref:System.Transactions.DistributedTransactionPermission> viene richiesta ogni volta che viene eseguita l'escalation della gestione della transazione in modo che questa venga gestita da Microsoft Distributed Transaction Coordinator (MSDTC). Questo tipo di scenario utilizza risorse a livello di processo e in particolare una risorsa globale, ovvero lo spazio riservato nel log di MSDTC. Un esempio di questo utilizzo è un front-end Web per un database o per un'applicazione che usa un database come parte dei servizi forniti.  
  
 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] include un set di livelli di attendibilità proprio, a cui associa un set specifico di autorizzazioni tramite file dei criteri. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][File dei criteri e i livelli di attendibilità ASP.NET](http://msdn.microsoft.com/library/f897c794-10d3-414c-86b7-59b66564bbf1). Quando si installa inizialmente Windows SDK, nessuno dei file dei criteri predefiniti di [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] è associato a <xref:System.Transactions.DistributedTransactionPermission>. Di conseguenza, quando viene eseguita l'escalation di una transazione appartenente a un'applicazione [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] in modo che venga gestita tramite MSDTC, l'escalation non riesce e viene generata un'eccezione <xref:System.Security.SecurityException> perché la transazione non ha l'autorizzazione <xref:System.Transactions.DistributedTransactionPermission>. Per abilitare l'escalation delle transazioni in un ambiente [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] parzialmente attendibile, è necessario concedere l'autorizzazione <xref:System.Transactions.DistributedTransactionPermission> agli stessi livelli di attendibilità predefiniti indicati nell'autorizzazione <xref:System.Data.SqlClient.SqlClientPermission>. A questo scopo, è possibile configurare un livello di attendibilità e un file dei criteri personalizzati oppure modificare i file dei criteri predefiniti, ovvero **Web_hightrust.config** e **Web_mediumtrust.config**.  
  
 Per modificare i file dei criteri, aggiungere un **SecurityClass** elemento per **DistributedTransactionPermission** per il **SecurityClasses** elemento sotto il  **PolicyLevel** elemento e aggiungere un corrispondente **IPermission** elemento sotto il [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] **NamedPermissionSet** per System. Transactions. Queste modifiche vengono mostrate nel file di configurazione seguente.  
  
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
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] , vedere [Elemento securityPolicy (schema delle impostazioni ASP.NET)](http://msdn.microsoft.com/en-us/469d8d22-d263-46bb-8400-40d8d027faba).  
  
## <a name="dynamic-compilation"></a>Compilazione dinamica  
 Se si vuole importare e usare <xref:System.Transactions> in un'applicazione [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] compilata dinamicamente all'accesso, è necessario inserire nel file di configurazione un riferimento all'assembly <xref:System.Transactions> . In particolare, il riferimento deve essere aggiunto nella sezione **compilation**/**assemblies** del file di configurazione **Web.config** radice predefinito oppure nel file di configurazione di un'applicazione Web specifica. Nell'esempio che segue viene illustrato quanto descritto.  
  
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
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Elemento add per assembly per la compilazione (scheda delle impostazioni ASP.NET)](http://msdn.microsoft.com/en-us/602197e8-108d-4249-b752-ba2a318f75e4).  
  
## <a name="see-also"></a>Vedere anche  
 [File dei criteri e i livelli di attendibilità di ASP.NET](http://msdn.microsoft.com/library/f897c794-10d3-414c-86b7-59b66564bbf1)  
 [Elemento securityPolicy (Schema delle impostazioni ASP.NET)](http://msdn.microsoft.com/en-us/469d8d22-d263-46bb-8400-40d8d027faba)  
 [Escalation della gestione delle transazioni](../../../../docs/framework/data/transactions/transaction-management-escalation.md)
