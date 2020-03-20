---
title: <generatePublisherEvidence> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
ms.openlocfilehash: 24a5ea02992a5bce681b5bab4fb7f75505bd225d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154114"
---
# <a name="generatepublisherevidence-element"></a>\<Elemento generatePublisherEvidence>
Specifica se il <xref:System.Security.Policy.Publisher> runtime crea l'evidenza per la sicurezza dall'accesso di codice.  
  
[**\<>di configurazione**](../configuration-element.md)\
&nbsp;&nbsp;[**\<>di runtime**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<generare PublisherEvidence>**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<generatePublisherEvidence
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributes  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`enabled`|Attributo obbligatorio.<br /><br /> Specifica se il <xref:System.Security.Policy.Publisher> runtime crea l'evidenza.|  
  
## <a name="enabled-attribute"></a>Attributo enabled  
  
|valore|Descrizione|  
|-----------|-----------------|  
|`false`|Non crea <xref:System.Security.Policy.Publisher> prove.|  
|`true`|Crea <xref:System.Security.Policy.Publisher> prove. Questa è la modalità predefinita.|  
  
### <a name="child-elements"></a>Elementi figlio  
 No.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.|  
  
## <a name="remarks"></a>Osservazioni  
  
> [!NOTE]
> In .NET Framework 4 e versioni successive, questo elemento non ha alcun effetto sui tempi di caricamento dell'assembly. Per ulteriori informazioni, vedere la sezione "Semplificazione dei criteri di sicurezza" in Modifiche alla [protezione](../../../security/security-changes.md).  
  
 Common Language Runtime (CLR) tenta di verificare la firma <xref:System.Security.Policy.Publisher> Authenticode in fase di caricamento per creare l'evidenza per l'assembly. Tuttavia, per impostazione predefinita, la maggior parte delle applicazioni non richiedono <xref:System.Security.Policy.Publisher> prove. I criteri CAS standard <xref:System.Security.Policy.PublisherMembershipCondition>non si basano sul file . È consigliabile evitare il costo di avvio non necessario associato alla verifica della firma dell'editore, a meno che l'applicazione non venga eseguita in un computer con criteri CAS personalizzati o non intenda soddisfare le richieste <xref:System.Security.Permissions.PublisherIdentityPermission> in un ambiente parzialmente attendibile. Le richieste di autorizzazioni di identità hanno sempre esito positivo in un ambiente con attendibilità totale.  
  
> [!NOTE]
> È consigliabile che `<generatePublisherEvidence>` i servizi utilizzino l'elemento per migliorare le prestazioni di avvio.  L'utilizzo di questo elemento consente inoltre di evitare ritardi che possono causare un timeout e l'annullamento dell'avvio del servizio.  
  
## <a name="configuration-file"></a>File di configurazione  
 Questo elemento può essere utilizzato solo nel file di configurazione dell'applicazione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene `<generatePublisherEvidence>` illustrato come utilizzare l'elemento per disabilitare il controllo dei criteri editore CAS per un'applicazione.  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Schema delle impostazioni di runtime](index.md)
- [Schema del file di configurazione](../index.md)
