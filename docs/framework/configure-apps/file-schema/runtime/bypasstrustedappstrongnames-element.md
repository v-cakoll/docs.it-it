---
title: <bypassTrustedAppStrongNames> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- strong-name bypass feature
- bypassTrustedAppStrongNames element
- strong-named assemblies, loading into trusted application domains
- <bypassTrustedAppStrongNames> element
ms.assetid: 71b2ebf6-3843-41e2-ad52-ffa5cd083a40
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aac7079d941e6774ca6c00fbece8ff72fbf3f0e1
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663879"
---
# <a name="bypasstrustedappstrongnames-element"></a>Elemento \<bypassTrustedAppStrongNames>
Specifica se ignorare la convalida di nomi sicuri in assembly con attendibilità totale caricati in un attendibilità <xref:System.AppDomain>totale.  
  
 \<configuration>  
\<runtime>  
\<bypassTrustedAppStrongNames>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<bypassTrustedAppStrongNames    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`enabled`|Attributo obbligatorio.<br /><br /> Specifica se è abilitata la funzionalità bypass che consente di evitare la convalida di nomi sicuri per gli assembly con attendibilità totale. Quando questa funzionalità è abilitata, i nomi sicuri non vengono convalidati per correttezza quando viene caricato l'assembly. Il valore predefinito è `true`.|  
  
## <a name="enabled-attribute"></a>Attributo enabled  
  
|Valore|DESCRIZIONE|  
|-----------|-----------------|  
|`true`|Le firme con nome sicuro in assembly con attendibilità totale non vengono convalidate quando gli assembly vengono caricati in un <xref:System.AppDomain>attendibilità totale. Questa è l'impostazione predefinita.|  
|`false`|Le firme con nome sicuro per gli assembly con attendibilità totale vengono convalidate quando gli assembly vengono caricati in <xref:System.AppDomain>un attendibilità totale. La firma con nome sicuro viene verificata solo per la correttezza della firma; non viene confrontato con un altro nome sicuro per una corrispondenza.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|  
  
## <a name="remarks"></a>Note  
 La funzionalità di bypass con nome sicuro evita l'overhead della verifica della firma con nome sicuro degli assembly con attendibilità totale.  
  
 Questa funzionalità si applica a qualsiasi assembly firmato con un nome sicuro e che ha le caratteristiche seguenti:  
  
- Completamente attendibile senza <xref:System.Security.Policy.StrongName> l'evidenza, ad esempio con `MyComputer` l'evidenza della zona.  
  
- Viene caricato in un dominio <xref:System.AppDomain> completamente attendibile.  
  
- Viene caricato da una località nell'ambito della proprietà <xref:System.AppDomainSetup.ApplicationBase%2A> di <xref:System.AppDomain>.  
  
- Non ha firma ritardata.  
  
> [!NOTE]
>  Se la funzionalità bypass è stata disattivata per tutte le applicazioni del computer utilizzando una chiave del registro di sistema, questa impostazione del file di configurazione non ha alcun effetto. Per altre informazioni, vedere [Procedura: Disabilitare la funzionalità che consente di ignorare il nome sicuro](../../../app-domains/how-to-disable-the-strong-name-bypass-feature.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come specificare il comportamento che convalida la firma con nome sicuro in assembly con attendibilità totale.  
  
```xml  
<configuration>  
   <runtime>  
      <bypassTrustedAppStrongNames enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Schema delle impostazioni di runtime](index.md)
- [Schema dei file di configurazione](../index.md)
- [Procedura: Disabilitare la funzionalità che consente di ignorare il nome sicuro](../../../app-domains/how-to-disable-the-strong-name-bypass-feature.md)
