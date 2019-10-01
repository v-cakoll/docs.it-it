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
ms.openlocfilehash: 15f4d10a70dc3c6abd32869f5b7b0006a799b4bf
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698038"
---
# <a name="module-element-network-settings"></a>Elemento > \<module (impostazioni di rete)
Aggiunge un nuovo modulo proxy all'applicazione.  
  
[ **\<configuration>** ](../configuration-element.md)  
&nbsp; @ no__t-1[ **@no__t -4system. net >** ](system-net-element-network-settings.md)  
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<defaultProxy >** ](defaultproxy-element-network-settings.md)  
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<module >**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<module   
  type="type_fullname, assembly_fullname"   
/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|**Attribute**|**Descrizione**|  
|-------------------|---------------------|  
|`type`|Il nome completo del tipo (indicato dalla proprietà <xref:System.Type.FullName%2A>) e il nome dell'assembly (indicato dalla proprietà <xref:System.Reflection.Assembly.FullName%2A>), separati da una virgola, che implementa il proxy.|  
  
### <a name="child-elements"></a>Elementi figlio  
 No.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|**Elemento**|**Descrizione**|  
|-----------------|---------------------|  
|[defaultProxy](defaultproxy-element-network-settings.md)|Configura il server proxy Hypertext Transfer Protocol (HTTP).|  
  
## <a name="remarks"></a>Note  
 L'elemento `module` registra le classi proxy che implementano l'interfaccia <xref:System.Net.IWebProxy>. Dopo la registrazione della classe proxy, `module` può essere utilizzato per richiedere informazioni mediante il proxy supportato.  
  
 Il valore dell'attributo `type` deve corrispondere al nome della classe del modulo e al nome della corrispondente libreria di collegamento dinamico (DLL).  
  
## <a name="configuration-files"></a>File di configurazione  
 Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene registrata una classe proxy personalizzata.  
  
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
