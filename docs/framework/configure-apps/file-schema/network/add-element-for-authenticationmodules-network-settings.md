---
title: Elemento <add> per authenticationModules (impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules/add
helpviewer_keywords:
- authenticationModules, add element
- add element, authenticationModules
- <authenticationModules>, add element
- <add> element, authenticationModules
ms.assetid: 333c5fb0-a2ab-4db8-8531-a7fe37bb9b5b
ms.openlocfilehash: a68434aaa118db60a502c2bcc0bb188b83b0f463
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698423"
---
# <a name="add-element-for-authenticationmodules-network-settings"></a>Elemento > \<add per authenticationModules (impostazioni di rete)
Aggiunge un modulo di autenticazione all'applicazione.  
  
[ **\<configuration>** ](../configuration-element.md)  
&nbsp; @ no__t-1[ **@no__t -4system. net >** ](system-net-element-network-settings.md)  
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<authenticationModules >** ](authenticationmodules-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Aggiungi >**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<add
  type="type_fullname, assembly_fullname"   
/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|**Attribute**|**Descrizione**|  
|-------------------|---------------------|  
|`type`|Il nome completo del tipo (indicato dalla proprietà <xref:System.Type.FullName%2A>) e il nome dell'assembly (indicato dalla proprietà <xref:System.Reflection.Assembly.FullName%2A>), separati da una virgola.|  
  
### <a name="child-elements"></a>Elementi figlio  
 No.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|**Elemento**|**Descrizione**|  
|-----------------|---------------------|  
|[authenticationModules](authenticationmodules-element-network-settings.md)|Specifica i moduli usati per autenticare le richieste di rete.|  
  
## <a name="remarks"></a>Note  
 Con l'elemento `add` viene aggiunto un modulo di autenticazione alla fine dell'elenco dei moduli di autenticazione registrati. I moduli di autenticazione vengono chiamati nell'ordine in cui sono stati aggiunti all'elenco.  
  
 Il valore dell'attributo `type` deve essere un nome di tipo valido e un nome di assembly corrispondente, separati da una virgola.  
  
## <a name="configuration-files"></a>File di configurazione  
 Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono abilitati i moduli di autenticazione predefiniti. È necessario sostituire i valori per Version e PublicKeyToken con i valori corretti per il modulo specificato.  
  
```xml  
<configuration>  
  <system.net>  
        <authenticationModules>  
            <add type="System.Net.DigestClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.NegotiateClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.KerberosClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.NtlmClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.BasicClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
        </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [Schema delle impostazioni di rete](index.md)
