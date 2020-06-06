---
title: <comContract>
ms.date: 03/30/2017
ms.assetid: 3f8e1c0c-cfdf-4c79-ac65-c64e9323a51c
ms.openlocfilehash: b499294af71ba230dcf985d4af1d013b1ca260cf
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850022"
---
# \<comContract>
Specifica un contratto del servizio COM+ Integration.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContracts>**](comcontracts.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<comContract>**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<comContracts>
  <comContract contract="String"
               namespace="String"
               name="String"
               requireSession="Boolean">
    <exposedMethods>
      <exposedMethod name="String" />
    </exposedMethods>
    <userDefinedTypes>
      <userDefinedType name="String"
                       typeLibID="String"
                       typeLibVersion="String"
                       typeDefID="String">
      </userDefinedType>
    </userDefinedTypes>
    <persistableTypes>
      <persistableType id="String"
                       name="String">
      </persistableType>
    </persistableTypes>
  </comContract>
</comContracts>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|contract|Stringa che contiene il tipo di contratto.|  
|name|Stringa che contiene il nome del contratto.|  
|namespace|Stringa che contiene lo spazio dei nomi del contratto.|  
|requiresSession|Valore booleano che specifica se il contratto può essere usato solo nelle associazioni con sessione. All'avvio del servizio, il runtime di integrazione verifica che questa impostazione sia coerente con il tipo di associazione da usare. Viene generata un'eccezione se una o più delle associazioni per il contratto sono in conflitto tra loro. Se questa proprietà è `false` e viene usato un canale unidirezionale in presenza di parametri [out], viene generata un'eccezione.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|persistableTypes|Tutti i tipi persistenti.|  
|userDefinedTypes|Raccolta di tipi definiti dall'utente che deve essere inclusa nel contratto di servizio.|  
|exposedMethods|Raccolta di metodi COM+ che vengono esposti quando l'interfaccia in un componente COM+ viene esposta come servizio Web.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|comContracts|Contiene una raccolta di elementi `comContract`.|  
  
## <a name="remarks"></a>Commenti  
 I contratti di servizio COM+ Integration sono attualmente limitati allo `http://tempuri.org` spazio dei nomi e il nome del contratto è derivato dall'interfaccia com di supporto. È tuttavia possibile specificare alternative usando la sezione `comContracts` e anche l'elemento `comContract` nel file di configurazione. Ad esempio, è possibile usare la configurazione seguente per specificare lo spazio dei nomi, il nome del contratto, i tipi definiti dall'utente da includere e altre impostazioni per un contratto di servizio.  
  
```xml  
<comContracts>
  <comContract contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"
               namespace="http://tempuri.org/5163B1E7-F0CF-4B6A-9A02-4AB654F34284"
               name="_Broker"
               requireSession="true">
    <exposedMethods>
      <exposedMethod name="BuyStock" />
      <exposedMethod name="SellStock" />
      <exposedMethod name="ExecuteTransaction" />
    </exposedMethods>
  </comContract>
</comContracts>
```  
  
 Quando il servizio viene inizializzato, gli spazi dei nomi specificati e i nomi del contratto vengono applicati alle descrizioni del servizio generate.  
  
## <a name="see-also"></a>Vedi anche

- <xref:System.ServiceModel.Configuration.ComContractElementCollection>
- <xref:System.ServiceModel.Configuration.ComContractElement>
- [\<comContracts>](comcontracts.md)
- [Integrazione con applicazioni COM+](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [Procedura: configurare le impostazioni del servizio COM+](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
