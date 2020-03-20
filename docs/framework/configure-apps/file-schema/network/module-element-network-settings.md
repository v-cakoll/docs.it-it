---
title: Elemento <module> (impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#module
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/module
helpviewer_keywords:
- module element
- <module> element
ms.assetid: 10318725-9666-4d65-ab61-b94c64e59f13
ms.openlocfilehash: ed28ae4a52085cbfa781b4baf2ee1eafbeff6eb4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154829"
---
# <a name="module-element-network-settings"></a>\<module> Element (Impostazioni di rete)
Aggiunge un nuovo modulo proxy all'applicazione.  

[**\<>di configurazione**](../configuration-element.md)\
&nbsp;&nbsp;[**\<>system.net**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<>defaultProxy**](defaultproxy-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>modulo**

## <a name="syntax"></a>Sintassi  
  
```xml  
<module
  type="type_fullname, assembly_fullname"
/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributes  
  
|**Attributo**|**Descrizione**|  
|-------------------|---------------------|  
|`type`|Il nome completo del <xref:System.Type.FullName%2A> tipo (indicato dalla proprietà) e il <xref:System.Reflection.Assembly.FullName%2A> nome dell'assembly (indicato dalla proprietà), separati da una virgola, che implementa il proxy.|  
  
### <a name="child-elements"></a>Elementi figlio  
 No.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|**Elemento**|**Descrizione**|  
|-----------------|---------------------|  
|[defaultProxy](defaultproxy-element-network-settings.md)|Configura il server proxy Hypertext Transfer Protocol (HTTP).|  
  
## <a name="remarks"></a>Osservazioni  
 L'elemento `module` registra le classi <xref:System.Net.IWebProxy> proxy che implementano l'interfaccia. Dopo la registrazione della classe proxy, `module` può essere utilizzato per richiedere informazioni mediante il proxy supportato.  
  
 Il valore `type` dell'attributo deve essere il nome della classe del modulo e il nome della corrispondente libreria a collegamento dinamico (DLL).  
  
## <a name="configuration-files"></a>File di configurazione  
 Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene registrato una classe proxy personalizzata.  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <module  
        type="Test.CustomWebProxy, TestProxy, Version=2.0.3600.0, Culture=neutral, PublicKeyToken=b23a5c561934e385"  
      />  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Net.IWebProxy?displayProperty=nameWithType>
- [Schema delle impostazioni di rete](index.md)
