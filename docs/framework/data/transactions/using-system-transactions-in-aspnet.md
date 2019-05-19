---
title: Uso di System.Transactions in ASP.NET
ms.date: 03/30/2017
ms.assetid: 1982c300-7ea6-4242-95ed-dc28ccfacac9
ms.openlocfilehash: 866d7b69fa6c18f6edfb48655b213e140a095a28
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2019
ms.locfileid: "65880227"
---
# <a name="using-systemtransactions-in-aspnet"></a>Uso di System.Transactions in ASP.NET
Questo argomento descrive il modo in cui è possibile utilizzare correttamente lo spazio dei nomi <xref:System.Transactions> all'interno di un'applicazione ASP.NET.  
  
## <a name="enable-distributedtransactionpermission-in-aspnet"></a>Abilitare DistributedTransactionPermission in ASP.NET  
 <xref:System.Transactions> supporta i chiamanti parzialmente attendibili ed è contrassegnato con l'attributo APTCA ( **AllowPartiallyTrustedCallers** ). I livelli di attendibilità per <xref:System.Transactions> sono definiti in base ai tipi di risorse (come memoria di sistema, risorse a livello di processo condivise, risorse a livello di sistema e altre risorse) esposti da <xref:System.Transactions> e in base al livello di attendibilità necessario per accedere a queste risorse. In un ambiente parzialmente attendibile un assembly con attendibilità non totale può usare solo le transazioni all'interno del dominio applicazione (in questo caso l'unica risorsa protetta è la memoria di sistema), a meno che non ottenga l'autorizzazione <xref:System.Transactions.DistributedTransactionPermission>.  
  
 L'autorizzazione<xref:System.Transactions.DistributedTransactionPermission> viene richiesta ogni volta che viene eseguita l'escalation della gestione della transazione in modo che questa venga gestita da Microsoft Distributed Transaction Coordinator (MSDTC). Questo tipo di scenario utilizza risorse a livello di processo e in particolare una risorsa globale, ovvero lo spazio riservato nel log di MSDTC. Un esempio di questo utilizzo è un front-end Web per un database o per un'applicazione che usa un database come parte dei servizi forniti.  
  
 ASP.NET dispone di un proprio set di livelli di attendibilità, a cui associa un set specifico di autorizzazioni utilizzando i file dei criteri. Per altre informazioni, vedere [livelli di Trust di ASP.NET e i file dei criteri](https://docs.microsoft.com/previous-versions/aspnet/wyts434y(v=vs.100)). Quando si installa inizialmente Windows SDK, nessuno dei file di criteri ASP.NET predefinito sono associati i <xref:System.Transactions.DistributedTransactionPermission>. Ne consegue che quando si tenta di eseguire l'escalation di una transazione appartenente a un'applicazione ASP.NET in modo che venga gestita tramite MSDTC, tale tentativo ha esito negativo e viene generata un'eccezione <xref:System.Security.SecurityException> in quanto la transazione non dispone dell'autorizzazione <xref:System.Transactions.DistributedTransactionPermission>. Per abilitare l'escalation delle transazioni in un ambiente ASP.NET parzialmente attendibile, è necessario concedere l'autorizzazione <xref:System.Transactions.DistributedTransactionPermission> agli stessi livelli di attendibilità predefiniti indicati nell'autorizzazione <xref:System.Data.SqlClient.SqlClientPermission>. A questo scopo, è possibile configurare un livello di attendibilità e un file dei criteri personalizzati oppure modificare i file dei criteri predefiniti, ovvero **Web_hightrust.config** e **Web_mediumtrust.config**.  
  
 Per modificare i file dei criteri, aggiungere un **SecurityClass** (elemento) per **DistributedTransactionPermission** per il **SecurityClasses** elemento sotto il  **PolicyLevel** elemento e aggiungere un corrispondente **IPermission** elemento sotto l'ASP.NET **NamedPermissionSet** per System. Transactions. Queste modifiche vengono mostrate nel file di configurazione seguente.  
  
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
  
 Per altre informazioni sui criteri di sicurezza ASP.NET, vedere [elemento securityPolicy (Schema delle impostazioni ASP.NET)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/zhs35b56(v=vs.100)).  
  
## <a name="dynamic-compilation"></a>Compilazione dinamica  
 Se si desidera importare e utilizzare lo spazio dei nomi <xref:System.Transactions> in un'applicazione ASP.NET compilata dinamicamente all'accesso, è necessario inserire nel file di configurazione un riferimento all'assembly <xref:System.Transactions>. In particolare, il riferimento deve essere aggiunto nella sezione **compilation**/**assemblies** del file di configurazione **Web.config** radice predefinito oppure nel file di configurazione di un'applicazione Web specifica. Nell'esempio che segue viene illustrato quanto descritto.  
  
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
  
 Per altre informazioni, vedere [elemento add per assemblies per compilation (Schema delle impostazioni ASP.NET)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/37e2zyhb(v=vs.100)).  
  
## <a name="see-also"></a>Vedere anche

- [I livelli di attendibilità di ASP.NET e i file dei criteri](https://docs.microsoft.com/previous-versions/aspnet/wyts434y(v=vs.100))
- [Elemento securityPolicy (Schema delle impostazioni ASP.NET)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/zhs35b56(v=vs.100))
- [Escalation della gestione delle transazioni](../../../../docs/framework/data/transactions/transaction-management-escalation.md)
