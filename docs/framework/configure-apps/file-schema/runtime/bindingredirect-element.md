---
title: <bindingRedirect> Elemento
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/bindingRedirect
- http://schemas.microsoft.com/.NetConfiguration/v2.0#bindingRedirect
helpviewer_keywords:
- <bindingRedirect> element
- container tags, <bindingRedirect> element
- bindingRedirect element
ms.assetid: 67784ecd-9663-434e-bd6a-26975e447ac0
ms.openlocfilehash: 7d51ef5c4107fc6a40a472a660f53bb0ded59683
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252781"
---
# <a name="bindingredirect-element"></a>\<Elemento > bindingRedirect
Reindirizza una versione dell'assembly in un'altra.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> di runtime**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di associazione**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> dependentAssembly**](dependentassembly-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<bindingRedirect>**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
   <bindingRedirect    
oldVersion="existing assembly version"  
newVersion="new assembly version"/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`oldVersion`|Attributo obbligatorio.<br /><br /> Specifica la versione dell'assembly richiesta in origine. Il formato di un numero di versione dell'assembly è *Major. minor. Build. Revision*. I valori validi per ogni parte del numero di versione sono compresi tra 0 e 65535.<br /><br /> È inoltre possibile specificare una gamma di versioni nel seguente formato:<br /><br /> *n.n.n.n - n.n.n.n*|  
|`newVersion`|Attributo obbligatorio.<br /><br /> Specifica la versione dell'assembly da utilizzare al posto della versione richiesta originariamente nel formato: *n* . n. n. n<br /><br /> Questo valore può specificare una versione precedente di `oldVersion`.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|DESCRIZIONE|  
|-------------|-----------------|  
|Nessuna||  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`assemblyBinding`|Contiene le informazioni sul reindirizzamento della versione degli assembly e i relativi percorsi.|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`dependentAssembly`|Incapsula i criteri di associazione e il percorso dell'assembly per ciascun assembly. Utilizzare un elemento dependentAssembly per ciascun assembly.|  
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|  
  
## <a name="remarks"></a>Note  
 Quando si compila un'applicazione .NET Framework in base a un assembly con un nome sicuro, per impostazione predefinita tale versione dell'assembly viene utilizzata dall'applicazione in fase di esecuzione, anche se è disponibile una nuova versione. È possibile tuttavia configurare l'applicazione in modo che venga eseguita in base a una versione più recente dell'assembly. Per informazioni dettagliate sul modo in cui il runtime usa questi file per determinare quale versione dell'assembly usare, vedere [come il runtime individua gli assembly](../../../deployment/how-the-runtime-locates-assemblies.md).  
  
 È possibile reindirizzare più versioni di assembly includendo più elementi `bindingRedirect` in un elemento `dependentAssembly`. È inoltre possibile reindirizzare una versione più recente a una versione precedente dell'assembly.  
  
 Il reindirizzamento esplicito dell'associazione di assembly in un file di configurazione di un'applicazione richiede un'autorizzazione di sicurezza, che vale per il reindirizzamento degli assembly .NET Framework e di quelli di altri produttori. L'autorizzazione viene concessa impostando <xref:System.Security.Permissions.SecurityPermissionFlag> il flag <xref:System.Security.Permissions.SecurityPermission>su. Per altre informazioni, vedere [autorizzazione di sicurezza](../../assembly-binding-redirection-security-permission.md)per il reindirizzamento dell'associazione di assembly.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come reindirizzare una versione dell'assembly a un'altra.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <bindingRedirect oldVersion="1.0.0.0"  
                             newVersion="2.0.0.0"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Schema delle impostazioni di runtime](index.md)
- [Schema dei file di configurazione](../index.md)
- [Reindirizzamento delle versioni di assembly](../../redirect-assembly-versions.md)
