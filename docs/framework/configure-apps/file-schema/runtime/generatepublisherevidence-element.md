---
title: <generatePublisherEvidence> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
ms.openlocfilehash: b04ef53d6e9c3d954b0925ea8634b3d220b36af7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73116580"
---
# <a name="generatepublisherevidence-element"></a>\<elemento > generatePublisherEvidence
Specifica se il runtime crea <xref:System.Security.Policy.Publisher> evidenza per la sicurezza dall'accesso di codice (CAS).  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) \
&nbsp;&nbsp;&nbsp;&nbsp; **\<generatePublisherEvidence >**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<generatePublisherEvidence    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`enabled`|Attributo obbligatorio.<br /><br /> Specifica se il runtime crea <xref:System.Security.Policy.Publisher> evidenza.|  
  
## <a name="enabled-attribute"></a>Attributo enabled  
  
|Value|Descrizione|  
|-----------|-----------------|  
|`false`|Non crea <xref:System.Security.Policy.Publisher> evidenza.|  
|`true`|Crea <xref:System.Security.Policy.Publisher> evidenza. Questa è l'impostazione predefinita.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuna.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.|  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
> In .NET Framework 4 e versioni successive, questo elemento non ha alcun effetto sui tempi di caricamento degli assembly. Per ulteriori informazioni, vedere la sezione "semplificazione dei criteri di sicurezza" in [modifiche della sicurezza](../../../security/security-changes.md).  
  
 Il Common Language Runtime (CLR) tenta di verificare la firma Authenticode in fase di caricamento per creare <xref:System.Security.Policy.Publisher> evidenza per l'assembly. Per impostazione predefinita, tuttavia, la maggior parte delle applicazioni non necessita di <xref:System.Security.Policy.Publisher> evidenze. I criteri CAS standard non si basano sul <xref:System.Security.Policy.PublisherMembershipCondition>. È consigliabile evitare il costo di avvio non necessario associato alla verifica della firma del server di pubblicazione, a meno che l'applicazione non venga eseguita in un computer con criteri di protezione accesso alla classe personalizzati o si intenda soddisfare le richieste di <xref:System.Security.Permissions.PublisherIdentityPermission> in un ambiente parzialmente attendibile. (Le richieste di autorizzazioni di identità hanno sempre esito positivo in un ambiente con attendibilità totale).  
  
> [!NOTE]
> È consigliabile che i servizi usino l'elemento `<generatePublisherEvidence>` per migliorare le prestazioni di avvio.  L'uso di questo elemento consente inoltre di evitare ritardi che possono causare un timeout e l'annullamento dell'avvio del servizio.  
  
## <a name="configuration-file"></a>File di configurazione  
 Questo elemento può essere utilizzato solo nel file di configurazione dell'applicazione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come utilizzare l'elemento `<generatePublisherEvidence>` per disabilitare il controllo dei criteri di pubblicazione CAS per un'applicazione.  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Schema delle impostazioni di runtime](index.md)
- [Schema dei file di configurazione](../index.md)
