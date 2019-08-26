---
title: 'Procedura: Modificare il file di configurazione del computer per abilitare il supporto IPv6'
ms.date: 03/30/2017
ms.assetid: 5611b677-b9cc-43b8-a434-60e18d89aada
ms.openlocfilehash: af6eb8a334108c988967a555024b524e27d40f58
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69959071"
---
# <a name="how-to-modify-the-computer-configuration-file-to-enable-ipv6-support"></a>Procedura: Modificare il file di configurazione del computer per abilitare il supporto IPv6
L'esempio di codice seguente mostra come modificare il file di configurazione del computer, *machine.config*, per abilitare il supporto di IPv6. Il file *machine.config* è archiviato nella cartella *%Windir%\Microsoft.NET\Framework* nella directory in cui è installato Windows. Esiste un file *machine.config* separato nelle cartelle *%Windir%\Microsoft.NET\Framework* per ogni versione di .NET Framework installata nel computer, ad esempio *C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\machine.config*.  
  
 Queste impostazioni possono essere effettuate anche nel file di configurazione dell'applicazione, che ha la precedenza sul file di configurazione del computer.  
  
 Per .NET Framework versione 1.1 e versioni precedenti, il valore dell'opzione di configurazione **ipv6 enabled** specifica se i membri della classe <xref:System.Net.Dns?displayProperty=nameWithType> restituiscono indirizzi IPv6.  
  
 Per .NET Framework versione 2.0 e versioni successive, se Windows supporta IPv6, tutti i membri della classe <xref:System.Net.Dns?displayProperty=nameWithType> (ad esempio, il metodo <xref:System.Net.Dns.GetHostEntry%2A?displayProperty=nameWithType>) restituiscono indirizzi IPv6 con una limitazione. I membri obsoleti della classe <xref:System.Net.Dns?displayProperty=nameWithType> (ad esempio, il metodo <xref:System.Net.Dns.Resolve%2A?displayProperty=nameWithType>) leggeranno e riconosceranno il valore nel file di configurazione.  
  
> [!NOTE]
> Per .NET Framework versione 2.0 e versioni successive, IPv6 è abilitato per impostazione predefinita. Per .NET Framework versione 1.1 e versioni precedenti, IPv6 è disabilitato per impostazione predefinita.  
  
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

- [Indirizzamento IPv6](../../../docs/framework/network-programming/ipv6-addressing.md)
- [Schema delle impostazioni di rete](../../../docs/framework/configure-apps/file-schema/network/index.md)
- [Elemento \<ipv6> (impostazioni di rete)](../../../docs/framework/configure-apps/file-schema/network/ipv6-element-network-settings.md)
