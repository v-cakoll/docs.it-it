---
title: 'Procedura: Modificare il file di configurazione del computer per abilitare il supporto IPv6'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5611b677-b9cc-43b8-a434-60e18d89aada
caps.latest.revision: "18"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 696aeb619f14a5ebe9a760cbd78a0d0fa876edc0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-modify-the-computer-configuration-file-to-enable-ipv6-support"></a>Procedura: Modificare il file di configurazione del computer per abilitare il supporto IPv6
L'esempio di codice seguente mostra come modificare il file di configurazione del computer, *machine.config*, per abilitare il supporto di IPv6. Il file *machine.config* è archiviato nella cartella *%Windir%\Microsoft.NET\Framework* nella directory in cui è installato Windows. Esiste un file *machine.config* separato nelle cartelle *%Windir%\Microsoft.NET\Framework* per ogni versione di .NET Framework installata nel computer, ad esempio *C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\machine.config*.  
  
 Queste impostazioni possono essere effettuate anche nel file di configurazione dell'applicazione, che ha la precedenza sul file di configurazione del computer.  
  
 Per .NET Framework versione 1.1 e versioni precedenti, il valore dell'opzione di configurazione **ipv6 enabled** specifica se i membri della classe <xref:System.Net.Dns?displayProperty=nameWithType> restituiscono indirizzi IPv6.  
  
 Per .NET Framework versione 2.0 e versioni successive, se Windows supporta IPv6, tutti i membri della classe <xref:System.Net.Dns?displayProperty=nameWithType> (ad esempio, il metodo <xref:System.Net.Dns.GetHostEntry%2A?displayProperty=nameWithType>) restituiscono indirizzi IPv6 con una limitazione. I membri obsoleti della classe <xref:System.Net.Dns?displayProperty=nameWithType> (ad esempio, il metodo <xref:System.Net.Dns.Resolve%2A?displayProperty=nameWithType>) leggeranno e riconosceranno il valore nel file di configurazione.  
  
> [!NOTE]
>  Per .NET Framework versione 2.0 e versioni successive, IPv6 è abilitato per impostazione predefinita. Per .NET Framework versione 1.1 e versioni precedenti, IPv6 è disabilitato per impostazione predefinita.  
  
## <a name="example"></a>Esempio  
  
```xml  
<system.net>  
    …………  
    <settings>  
        …………  
        <ipv6 enabled="true"/>   
    ……………  
    </settings>  
    ………………  
<system.net>  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Indirizzamento IPv6](../../../docs/framework/network-programming/ipv6-addressing.md)  
 [Schema delle impostazioni di rete](../../../docs/framework/configure-apps/file-schema/network/index.md)  
 [Elemento \<ipv6> (impostazioni di rete)](../../../docs/framework/configure-apps/file-schema/network/ipv6-element-network-settings.md)
