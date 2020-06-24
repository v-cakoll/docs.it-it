---
title: Uso di System.Transactions in ASP.NET
description: Utilizzare System. Transactions all'interno di un'applicazione ASP.NET. Abilitare le autorizzazioni per le transazioni distribuite e utilizzare la compilazione dinamica.
ms.date: 03/30/2017
ms.assetid: 1982c300-7ea6-4242-95ed-dc28ccfacac9
ms.openlocfilehash: 48907faf99953e34d045a1e0d79eed8a788187b5
ms.sourcegitcommit: 6219b1e1feccb16d88656444210fed3297f5611e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/22/2020
ms.locfileid: "85141644"
---
# <a name="using-systemtransactions-in-aspnet"></a>Uso di System.Transactions in ASP.NET
Questo argomento descrive il modo in cui è possibile utilizzare correttamente lo spazio dei nomi <xref:System.Transactions> all'interno di un'applicazione ASP.NET.

## <a name="enable-distributedtransactionpermission-in-aspnet"></a>Abilitare DistributedTransactionPermission in ASP.NET
 <xref:System.Transactions>supporta chiamanti parzialmente attendibili ed è contrassegnato con l' `AllowPartiallyTrustedCallers` attributo (APTCA). I livelli di attendibilità per <xref:System.Transactions> sono definiti in base ai tipi di risorse (ad esempio memoria di sistema, risorse a livello di processo condivise, risorse a livello di sistema e altre risorse) esposte <xref:System.Transactions> da e il livello di attendibilità necessario per accedere a tali risorse. In un ambiente parzialmente attendibile un assembly con attendibilità non totale può usare solo le transazioni all'interno del dominio applicazione (in questo caso l'unica risorsa protetta è la memoria di sistema), a meno che non ottenga l'autorizzazione <xref:System.Transactions.DistributedTransactionPermission>.

 L'autorizzazione<xref:System.Transactions.DistributedTransactionPermission> viene richiesta ogni volta che viene eseguita l'escalation della gestione della transazione in modo che questa venga gestita da Microsoft Distributed Transaction Coordinator (MSDTC). Questo tipo di scenario utilizza risorse a livello di processo e in particolare una risorsa globale, ovvero lo spazio riservato nel log di MSDTC. Un esempio di questo utilizzo è un front-end Web per un database o per un'applicazione che usa un database come parte dei servizi forniti.

 ASP.NET dispone di un proprio set di livelli di attendibilità, a cui associa un set specifico di autorizzazioni utilizzando i file dei criteri. Per altre informazioni, vedere [ASP.NET Trust Levels and Policy Files](https://docs.microsoft.com/previous-versions/aspnet/wyts434y(v=vs.100)). Quando si installa inizialmente il Windows SDK, nessuno dei file dei criteri ASP.NET predefiniti è associato a <xref:System.Transactions.DistributedTransactionPermission> . Ne consegue che quando si tenta di eseguire l'escalation di una transazione appartenente a un'applicazione ASP.NET in modo che venga gestita tramite MSDTC, tale tentativo ha esito negativo e viene generata un'eccezione <xref:System.Security.SecurityException> in quanto la transazione non dispone dell'autorizzazione <xref:System.Transactions.DistributedTransactionPermission>. Per abilitare l'escalation delle transazioni in un ambiente ASP.NET parzialmente attendibile, è necessario concedere l'autorizzazione <xref:System.Transactions.DistributedTransactionPermission> agli stessi livelli di attendibilità predefiniti indicati nell'autorizzazione <xref:System.Data.SqlClient.SqlClientPermission>. A questo scopo, è possibile configurare un livello di attendibilità e un file dei criteri personalizzati oppure modificare i file dei criteri predefiniti, ovvero **Web_hightrust.config** e **Web_mediumtrust.config**.

 Per modificare i file dei criteri, aggiungere un `SecurityClass` elemento per `DistributedTransactionPermission` all' `SecurityClasses` elemento sotto l' `PolicyLevel` elemento e aggiungere un `IPermission` elemento corrispondente in ASP.NET `NamedPermissionSet` per System. Transactions. Queste modifiche vengono mostrate nel file di configurazione seguente.

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

 Per ulteriori informazioni sui criteri di sicurezza di ASP.NET, vedere [elemento securityPolicy (schema delle impostazioni ASP.NET)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/zhs35b56(v=vs.100)).

## <a name="dynamic-compilation"></a>Compilazione dinamica
 Se si desidera importare e utilizzare lo spazio dei nomi <xref:System.Transactions> in un'applicazione ASP.NET compilata dinamicamente all'accesso, è necessario inserire nel file di configurazione un riferimento all'assembly <xref:System.Transactions>. In particolare, il riferimento deve essere aggiunto nella `compilation/assemblies` sezione del file di configurazione radice predefinito **Web.config** o in un file di configurazione di un'applicazione Web specifica. L'esempio seguente illustra questa operazione.

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

 Per ulteriori informazioni, vedere [elemento Add per gli assembly per la compilazione (schema delle impostazioni ASP.NET)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/37e2zyhb(v=vs.100)).

## <a name="see-also"></a>Vedere anche

- [Livelli di attendibilità ASP.NET e file di criteri](https://docs.microsoft.com/previous-versions/aspnet/wyts434y(v=vs.100))
- [Elemento securityPolicy (schema delle impostazioni ASP.NET)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/zhs35b56(v=vs.100))
- [Escalation della gestione delle transazioni](transaction-management-escalation.md)
