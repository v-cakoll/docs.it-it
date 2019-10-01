---
title: Elemento <authenticationModules> (impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#authenticationModules
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules
helpviewer_keywords:
- authenticationModules element
- <authenticationModules> element
ms.assetid: 10fcfaad-82ef-4692-871a-0aec9dfbe75e
ms.openlocfilehash: 4fe44deba951e5302518ed855589ad1b0ca75343
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699530"
---
# <a name="authenticationmodules-element-network-settings"></a>Elemento > \<authenticationModules (impostazioni di rete)
Specifica i moduli usati per autenticare le richieste di rete.  
  
[ **\<configuration>** ](../configuration-element.md)  
&nbsp; @ no__t-1[ **@no__t -4system. net >** ](system-net-element-network-settings.md)  
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 **\<authenticationModules >**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<authenticationModules>   
</authenticationModules>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
 No.  
  
### <a name="child-elements"></a>Elementi figlio  
  
|**Elemento**|**Descrizione**|  
|-----------------|---------------------|  
|[add](add-element-for-authenticationmodules-network-settings.md)|Aggiunge un modulo di autenticazione all'applicazione.|  
|[clear](clear-element-for-authenticationmodules-network-settings.md)|Cancella tutti i moduli di autenticazione dall'applicazione.|  
|[remove](remove-element-for-authenticationmodules-network-settings.md)|Rimuove un modulo di autenticazione dall'applicazione.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|**Elemento**|**Descrizione**|  
|-----------------|---------------------|  
|[system.net](system-net-element-network-settings.md)|Contiene le impostazioni di rete che specificano la modalità di connessione alla rete di .NET Framework.|  
  
## <a name="remarks"></a>Note  
 L'elemento `authenticationModule` specifica i moduli di autenticazione che eseguono il processo di autenticazione con un server. Un modulo di autenticazione deve implementare l'interfaccia <xref:System.Net.IAuthenticationModule>.  
  
## <a name="configuration-files"></a>File di configurazione  
 Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene abilitato un modulo di autenticazione. È necessario sostituire i valori per Version e PublicKeyToken con i valori corretti per il modulo specificato.  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <add type="System.Net.DigestClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [Schema delle impostazioni di rete](index.md)
