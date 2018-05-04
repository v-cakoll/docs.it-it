---
title: '&lt;assemblyIdentity&gt; elemento per &lt;runtime&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/assemblyIdentity
- http://schemas.microsoft.com/.NetConfiguration/v2.0#assemblyIdentity
helpviewer_keywords:
- <assemblyIdentity> element
- container tags, <assemblyIdentity> element
- assemblyIdentity element
ms.assetid: cea4d187-6398-4da4-af09-c1abc6a349c1
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 5d985d1620b7dec324c0113bcd5652cede044950
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltassemblyidentitygt-element-for-ltruntimegt"></a>&lt;assemblyIdentity&gt; elemento per &lt;runtime&gt;
Contiene le informazioni di identificazione dell'assembly.  
  
 \<configuration>  
\<runtime>  
\<assemblyBinding >  
\<dependentAssembly >  
\<assemblyIdentity >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
   <assemblyIdentity    
name="assembly name"  
publicKeyToken="public key token"  
culture="assembly culture"/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`name`|Attributo obbligatorio.<br /><br /> Il nome dell'assembly|  
|`culture`|Attributo facoltativo.<br /><br /> Stringa che specifica la lingua e paese/area geografica dell'assembly.|  
|`publicKeyToken`|Attributo facoltativo.<br /><br /> Un valore esadecimale che specifica il nome sicuro dell'assembly.|  
|`processorArchitecture`|Attributo facoltativo.<br /><br /> Uno dei valori di "x86", "amd64", "msil" oppure "ia64", che specifica l'architettura del processore per un assembly che contiene codice specifico del processore. I valori non sono rilevanti. Se l'attributo viene assegnato a qualsiasi altro valore, l'intero `<assemblyIdentity>` elemento viene ignorato. Vedere <xref:System.Reflection.ProcessorArchitecture>.|  
  
## <a name="processorarchitecture-attribute"></a>Attributo processorArchitecture  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|`amd64`|Solo processore AMD a 64 bit.|  
|`ia64`|Solo processore Intel a 64 bit.|  
|`msil`|Neutro rispetto al processore e bit per parola|  
|`x86`|Un processore Intel a 32 bit, nativo o l'ambiente Windows on Windows (WOW) su una piattaforma a 64 bit.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`assemblyBinding`|Contiene le informazioni sul reindirizzamento della versione degli assembly e i relativi percorsi.|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`dependentAssembly`|Incapsula i criteri di associazione e il percorso dell'assembly per ciascun assembly. Utilizzare uno `<dependentAssembly>` elemento per ogni assembly.|  
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|  
  
## <a name="remarks"></a>Note  
 Ogni  **\<dependentAssembly >** l'elemento deve avere uno  **\<assemblyIdentity >** elemento figlio.  
  
 Se il `processorArchitecture` attributo è presente, il `<assemblyIdentity>` elemento si applica solo agli assembly con l'architettura del processore corrispondente. Se il `processorArchitecture` attributo non è presente, il `<assemblyIdentity>` elemento può essere applicato a un assembly con qualsiasi architettura del processore.  
  
 Nell'esempio seguente viene illustrato un file di configurazione per due assembly con lo stesso nome che hanno come destinazione due differenti architetture del processore due e versioni di cui non sono state mantenute la sincronizzazione. Quando l'applicazione esegue su x86 piattaforma primo `<assemblyIdentity>` si applica l'elemento e l'altra viene ignorata. Se l'applicazione viene eseguita su una piattaforma diversa da x86 o ia64, entrambi vengono ignorati.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="MyAssembly"  
                  publicKeyToken="14a739be0244c389"  
                  culture="neutral"  
                  processorArchitecture="x86" />  
            <bindingRedirect oldVersion= "1.0.0.0"   
                  newVersion="1.1.0.0" />  
         </dependentAssembly>  
         <dependentAssembly>  
            <assemblyIdentity name="MyAssembly"  
                  publicKeyToken="14a739be0244c389"  
                  culture="neutral"   
                  processorArchitecture="ia64" />  
            <bindingRedirect oldVersion="1.0.0.0"   
                  newVersion="2.0.0.0" />  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 Se un file di configurazione contiene un `<assemblyIdentity>` elemento senza `processorArchitecture` attributo e non contiene un elemento che corrisponde alla piattaforma, l'elemento senza il `processorArchitecture` viene utilizzato l'attributo.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come fornire informazioni relative a un assembly.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <!--Redirection and codeBase policy for myAssembly.-->  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Schema delle impostazioni di runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Schema dei file di configurazione](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [Reindirizzamento delle versioni di assembly](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)
