---
title: Impostazioni dei criteri della direttiva di runtime
ms.date: 03/30/2017
ms.assetid: cb52b1ef-47fd-4609-b69d-0586c818ac9e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9015ec35c2a3d13b986eb9524e4f2984d909eb21
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59098234"
---
# <a name="runtime-directive-policy-settings"></a>Impostazioni dei criteri della direttiva di runtime
> [!NOTE]
>  In questo argomento si fa riferimento a .NET Native Developer Preview, ovvero la versione preliminare del software, che è possibile scaricare dal [sito Web di Microsoft Connect](https://go.microsoft.com/fwlink/?LinkId=394611) (è necessaria la registrazione).  
  
 Le impostazioni dei criteri della direttiva di runtime per .NET Native determinano la disponibilità di metadati per i tipi e i membri dei tipi al runtime. Senza i metadati necessari, le operazioni che si basano su reflection, serializzazione e deserializzazione o sul marshalling dei tipi .NET Framework a COM o Windows Runtime possono avere esito negativo e generare un'eccezione. Le eccezioni più comuni sono [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) e (nel caso dell'interoperabilità) [MissingInteropDataException](../../../docs/framework/net-native/missinginteropdataexception-class-net-native.md).  
  
 Le impostazioni dei criteri di runtime sono controllate da un file di direttive di runtime (.rd.xml). Ogni direttiva di runtime definisce i criteri per un elemento di programma specifico, ad esempio un assembly (elemento [\<Assembly>](../../../docs/framework/net-native/assembly-element-net-native.md)), un tipo (elemento [\<Type>](../../../docs/framework/net-native/type-element-net-native.md)) o un metodo (elemento [\<Method>](../../../docs/framework/net-native/method-element-net-native.md)). La direttiva include uno o più attributi che definiscono i tipi di criteri di reflection, i tipi di criteri di serializzazione e i tipi di criteri di interoperabilità discussi nella sezione successiva. Il valore dell'attributo definisce l'impostazione dei criteri.  
  
## <a name="policy-types"></a>Tipi di criteri  
 I file di direttive di runtime riconoscono tre categorie di tipi di criteri: reflection, serializzazione e interoperabilità.  
  
-   I tipi di criteri di reflection determinano i metadati disponibili per la reflection al runtime:  
  
    -   `Activate` Controlla l'accesso in fase di esecuzione ai costruttori per abilitare l'attivazione di istanze.  
  
    -   `Browse` Controlla le query per informazioni su elementi del programma.  
  
    -   `Dynamic` controlli runtime l'accesso a tutti i tipi e membri per abilitare dynamic di programmazione.  
  
     Nella seguente tabella sono elencati i tipi di criteri di reflection e gli elementi di programma con cui possono essere usati.  
  
    |Elemento|Activate|Browse|Dynamic|  
    |-------------|--------------|------------|-------------|  
    |[\<Application>](../../../docs/framework/net-native/application-element-net-native.md)|✓|✓|✓|  
    |[\<Assembly>](../../../docs/framework/net-native/assembly-element-net-native.md)|✓|✓|✓|  
    |[\<AttributeImplies>](../../../docs/framework/net-native/attributeimplies-element-net-native.md)|✓|✓|✓|  
    |[\<Event>](../../../docs/framework/net-native/event-element-net-native.md)||✓|✓|  
    |[\<Campo >](../../../docs/framework/net-native/field-element-net-native.md)||✓|✓|  
    |[\<GenericParameter>](../../../docs/framework/net-native/genericparameter-element-net-native.md)|✓|✓|✓|  
    |[\<ImpliesType>](../../../docs/framework/net-native/impliestype-element-net-native.md)|✓|✓|✓|  
    |[\<Metodo >](../../../docs/framework/net-native/method-element-net-native.md)||✓|✓|  
    |[\<MethodInstantiation >](../../../docs/framework/net-native/methodinstantiation-element-net-native.md)||✓|✓|  
    |[\<Namespace >](../../../docs/framework/net-native/namespace-element-net-native.md)|✓|✓|✓|  
    |[\<Parameter>](../../../docs/framework/net-native/parameter-element-net-native.md)|✓|✓|✓|  
    |[\<Proprietà >](../../../docs/framework/net-native/property-element-net-native.md)||✓|✓|  
    |[\<Subtypes>](../../../docs/framework/net-native/subtypes-element-net-native.md)|✓|✓|✓|  
    |[\<tipo >](../../../docs/framework/net-native/type-element-net-native.md)|✓|✓|✓|  
    |[\<TypeInstantiation >](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|✓|✓|✓|  
    |[\<TypeParameter>](../../../docs/framework/net-native/typeparameter-element-net-native.md)|✓|✓|✓|  
  
-   I tipi di criteri di serializzazione determinano i metadati disponibili per la serializzazione e la deserializzazione al runtime:  
  
    -   `Serialize` Controlla l'accesso in fase di esecuzione ai costruttori, campi e proprietà per abilitare le istanze di tipi da serializzare in librerie di terze parti, ad esempio il serializzatore JSON Newtonsoft.  
  
    -   `DataContractSerializer` Controlla l'accesso in fase di esecuzione ai costruttori, campi e proprietà per abilitare le istanze di tipi da serializzare tramite il <xref:System.Runtime.Serialization.DataContractSerializer> classe.  
  
    -   `DataContractJsonSerializer` Controlla l'accesso in fase di esecuzione ai costruttori, campi e proprietà per abilitare le istanze di tipi da serializzare tramite il <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> classe.  
  
    -   `XmlSerializer` Controlla l'accesso in fase di esecuzione ai costruttori, campi e proprietà per abilitare le istanze di tipi da serializzare tramite il <xref:System.Xml.Serialization.XmlSerializer> classe.  
  
     Nella seguente tabella sono elencati i tipi di criteri di serializzazione e gli elementi di programma con cui possono essere usati.  
  
    |Elemento|Serialize|DataContractSerializer|DataContractJsonSerializer|XmlSerializer|  
    |-------------|---------------|----------------------------|--------------------------------|-------------------|  
    |[\<Application>](../../../docs/framework/net-native/application-element-net-native.md)|✓|✓|✓|✓|  
    |[\<Assembly>](../../../docs/framework/net-native/assembly-element-net-native.md)|✓|✓|✓|✓|  
    |[\<AttributeImplies>](../../../docs/framework/net-native/attributeimplies-element-net-native.md)|✓|✓|✓|✓|  
    |[\<Event>](../../../docs/framework/net-native/event-element-net-native.md)|||||  
    |[\<Campo >](../../../docs/framework/net-native/field-element-net-native.md)|✓||||  
    |[\<GenericParameter>](../../../docs/framework/net-native/genericparameter-element-net-native.md)|✓|✓|✓|✓|  
    |[\<ImpliesType>](../../../docs/framework/net-native/impliestype-element-net-native.md)|✓|✓|✓|✓|  
    |[\<Metodo >](../../../docs/framework/net-native/method-element-net-native.md)|||||  
    |[\<MethodInstantiation >](../../../docs/framework/net-native/methodinstantiation-element-net-native.md)|||||  
    |[\<Namespace >](../../../docs/framework/net-native/namespace-element-net-native.md)|✓|✓|✓|✓|  
    |[\<Parameter>](../../../docs/framework/net-native/parameter-element-net-native.md)|✓|✓|✓|✓|  
    |[\<Proprietà >](../../../docs/framework/net-native/property-element-net-native.md)|✓||||  
    |[\<Subtypes>](../../../docs/framework/net-native/subtypes-element-net-native.md)|✓|✓|✓|✓|  
    |[\<tipo >](../../../docs/framework/net-native/type-element-net-native.md)|✓|✓|✓|✓|  
    |[\<TypeInstantiation >](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|✓|✓|✓|✓|  
    |[\<TypeParameter>](../../../docs/framework/net-native/typeparameter-element-net-native.md)|✓|✓|✓|✓|  
  
-   I tipi di criteri di interoperabilità determinano i metadati disponibili al runtime per passare i tipi di riferimento, i tipi di valore e i puntatori a funzioni a COM e Windows Runtime:  
  
    -   `MarshalObject` Controlla il marshalling nativo a COM e il Runtime di Windows per i tipi di riferimento.  
  
    -   `MarshalDelegate` Controlla il marshalling dei tipi delegati come puntatori a funzione.  
  
    -   `MarshalStructure` Controlla il marshalling nativo a COM e il Runtime di Windows per i tipi di valore.  
  
     Nella seguente tabella sono elencati i tipi di criteri di interoperabilità e gli elementi di programma con cui possono essere usati.  
  
    |Elemento|MarshalObject|MarshalDelegate|MarshalStructure|  
    |-------------|-------------------|---------------------|----------------------|  
    |[\<Application>](../../../docs/framework/net-native/application-element-net-native.md)|✓|✓|✓|  
    |[\<Assembly>](../../../docs/framework/net-native/assembly-element-net-native.md)|✓|✓|✓|  
    |[\<AttributeImplies>](../../../docs/framework/net-native/attributeimplies-element-net-native.md)|✓|✓|✓|  
    |[\<Event>](../../../docs/framework/net-native/event-element-net-native.md)||||  
    |[\<Campo >](../../../docs/framework/net-native/field-element-net-native.md)||||  
    |[\<GenericParameter>](../../../docs/framework/net-native/genericparameter-element-net-native.md)|✓|✓|✓|  
    |[\<ImpliesType>](../../../docs/framework/net-native/impliestype-element-net-native.md)|✓|✓|✓|  
    |[\<Metodo >](../../../docs/framework/net-native/method-element-net-native.md)||||  
    |[\<MethodInstantiation >](../../../docs/framework/net-native/methodinstantiation-element-net-native.md)||||  
    |[\<Namespace >](../../../docs/framework/net-native/namespace-element-net-native.md)|✓|✓|✓|  
    |[\<Parameter>](../../../docs/framework/net-native/parameter-element-net-native.md)|✓|✓|✓|  
    |[\<Proprietà >](../../../docs/framework/net-native/property-element-net-native.md)||||  
    |[\<Subtypes>](../../../docs/framework/net-native/subtypes-element-net-native.md)|✓|✓|✓|  
    |[\<tipo >](../../../docs/framework/net-native/type-element-net-native.md)|✓|✓|✓|  
    |[\<TypeInstantiation >](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|✓|✓|✓|  
    |[\<TypeParameter>](../../../docs/framework/net-native/typeparameter-element-net-native.md)|✓|✓|✓|  
  
## <a name="policy-settings"></a>Impostazioni dei criteri  
 Ciascun tipo di criteri può essere impostato su uno dei valori elencati nella seguente tabella. Gli elementi che rappresentano i membri dei tipi supportano un set di impostazioni dei criteri diverso rispetto a quello degli altri elementi.  
  
|Impostazione dei criteri|Descrizione|`Assembly`, `Namespace`, `Type`, e `TypeInstantiation` elementi|`Event`, `Field`, `Method`, `MethodInstantiation`, e `Property` elementi|  
|--------------------|-----------------|-----------------------------------------------------------------------|--------------------------------------------------------------------------------|  
|`All`|Abilita i criteri per tutti i tipi e i membri non rimossi dalla catena di strumenti del .NET Native.|✓||  
|`Auto`|Specifica di usare i criteri predefiniti per il tipo di criteri di un determinato elemento di programma. Questa impostazione equivale all'omissione dei criteri per un determinato tipo di criteri. `Auto` in genere viene utilizzato per indicare che i criteri viene ereditato da un elemento padre.|✓|✓|  
|`Excluded`|Specifica che i criteri sono disabilitati per un determinato elemento di programma. Ad esempio, la direttiva di runtime:<br /><br /> `<Type Name="BusinessClasses.Person" Browse="Excluded" Dynamic="Excluded" />`<br /><br /> specifica che i metadati per la classe `BusinessClasses.Person` non sono disponibili né per sfogliare, né per creare dinamicamente un'istanza e modificare gli oggetti `Person`.|✓|✓|  
|`Included`|Abilita i criteri se sono disponibili i metadati per il tipo padre.||✓|  
|`Public`|Abilita i criteri per i tipi o i membri pubblici, a meno che la catena di strumenti non determini che il tipo o il membro non è necessario e lo rimuova. Questa impostazione è diversa da `Required Public`, che garantisce la disponibilità costante dei metadati per i tipi e i membri pubblici, anche quando la catena di strumenti li identifica come non necessari.|✓||  
|`PublicAndInternal`|Abilita i criteri per i tipi o i membri pubblici e interni, a meno che la catena di strumenti non determini che il tipo o il membro non è necessario e lo rimuova. Questa impostazione è diversa da `Required PublicAndInternal`, che assicura la disponibilità costante dei metadati per i tipi e i membri pubblici e interni, anche quando la catena di strumenti li identifica come non necessari.|✓||  
|`Required`|Specifica che i criteri per un membro sono abilitati e che i metadati sono disponibili anche se il membro sembra essere in uso.||✓|  
|`Required Public`|Abilita i criteri per i tipi o i membri pubblici e assicura la disponibilità costante dei metadati per i tipi e i membri pubblici. Questa impostazione è diversa da `Public`, che rende disponibili i metadati per i tipi e i membri pubblici solo se la catena di strumenti li identifica come necessari.|✓||  
|`Required PublicAndInternal`|Abilita i criteri per i tipi o i membri pubblici e interni e assicura che i metadati per i tipi e i membri pubblici e interni siano sempre disponibili. Questa impostazione è diversa da `PublicAndInternal`, che rende disponibili i metadati per i tipi e i membri pubblici e interni solo se la catena di strumenti li identifica come necessari.|✓||  
|`Required All`|Richiede alla catena di strumenti di mantenere tutti i tipi e i membri indipendentemente dal loro uso effettivo e abilita i relativi criteri.|✓||  
  
## <a name="see-also"></a>Vedere anche

- [Riferimento a file di configurazione di direttive di runtime (rd.xml)](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
- [Elementi direttiva di runtime](../../../docs/framework/net-native/runtime-directive-elements.md)
