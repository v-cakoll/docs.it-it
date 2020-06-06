---
title: <bypassTrustedAppStrongNames> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- strong-name bypass feature
- bypassTrustedAppStrongNames element
- strong-named assemblies, loading into trusted application domains
- <bypassTrustedAppStrongNames> element
ms.assetid: 71b2ebf6-3843-41e2-ad52-ffa5cd083a40
ms.openlocfilehash: 96361a6742d1d2f76cb237344189d3277d7c8069
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73739090"
---
# <a name="bypasstrustedappstrongnames-element"></a>\<bypassTrustedAppStrongNames> Elemento

Specifica se ignorare la convalida di nomi sicuri in assembly con attendibilità totale caricati in un attendibilità totale <xref:System.AppDomain> .

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<bypassTrustedAppStrongNames>**

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

|Valore|Description|
|-----------|-----------------|
|`true`|Le firme con nome sicuro in assembly con attendibilità totale non vengono convalidate quando gli assembly vengono caricati in un attendibilità totale <xref:System.AppDomain> . Questo è il valore predefinito.|
|`false`|Le firme con nome sicuro per gli assembly con attendibilità totale vengono convalidate quando gli assembly vengono caricati in un attendibilità totale <xref:System.AppDomain> . La firma con nome sicuro viene verificata solo per la correttezza della firma; non viene confrontato con un altro nome sicuro per una corrispondenza.|

### <a name="child-elements"></a>Elementi figlio

No.

### <a name="parent-elements"></a>Elementi padre

|Elemento|Descrizione|
|-------------|-----------------|
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|

## <a name="remarks"></a>Commenti

La funzionalità di bypass con nome sicuro evita l'overhead della verifica della firma con nome sicuro degli assembly con attendibilità totale.

Questa funzionalità si applica a qualsiasi assembly firmato con un nome sicuro e che ha le caratteristiche seguenti:

- Completamente attendibile senza l' <xref:System.Security.Policy.StrongName> evidenza, ad esempio con l' `MyComputer` evidenza della zona.

- Viene caricato in un dominio <xref:System.AppDomain> completamente attendibile.

- Viene caricato da una località nell'ambito della proprietà <xref:System.AppDomainSetup.ApplicationBase%2A> di <xref:System.AppDomain>.

- Non ha firma ritardata.

> [!NOTE]
> Se la funzionalità bypass è stata disattivata per tutte le applicazioni del computer utilizzando una chiave del registro di sistema, questa impostazione del file di configurazione non ha alcun effetto. Per altre informazioni, vedere [procedura: disabilitare la funzionalità di bypass con nome sicuro](../../../../standard/assembly/disable-strong-name-bypass-feature.md).

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato come specificare il comportamento che convalida la firma con nome sicuro in assembly con attendibilità totale.

```xml
<configuration>
   <runtime>
      <bypassTrustedAppStrongNames enabled="false"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a>Vedi anche

- [Schema delle impostazioni di runtime](index.md)
- [Schema del file di configurazione](../index.md)
- [Procedura: disabilitare la funzionalità di bypass con nome sicuro](../../../../standard/assembly/disable-strong-name-bypass-feature.md)
