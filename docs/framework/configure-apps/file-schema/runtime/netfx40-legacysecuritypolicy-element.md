---
title: Elemento < NetFx40_LegacySecurityPolicy >
ms.date: 03/30/2017
helpviewer_keywords:
- <NetFx40_LegacySecurityPolicy> element
- NetFx40_LegacySecurityPolicy element
ms.assetid: 07132b9c-4a72-4710-99d7-e702405e02d4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2cd6f937811ae503dd4de7ff989510c4eb8b8933
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252450"
---
# <a name="netfx40_legacysecuritypolicy-element"></a>\<Elemento > NetFx40_LegacySecurityPolicy

Specifica se il runtime usa i criteri di sicurezza per l'accesso di codice legacy.

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> di runtime**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<> NetFx40_LegacySecurityPolicy**  

## <a name="syntax"></a>Sintassi

```xml
<NetFx40_LegacySecurityPolicy
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a>Attributi ed elementi

Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.

### <a name="attributes"></a>Attributi

|Attributo|Descrizione|
|---------------|-----------------|
|`enabled`|Attributo obbligatorio.<br /><br /> Specifica se il runtime usa i criteri CAS legacy.|

## <a name="enabled-attribute"></a>Attributo enabled

|Valore|DESCRIZIONE|
|-----------|-----------------|
|`false`|Il runtime non usa i criteri CAS legacy. Questa è l'impostazione predefinita.|
|`true`|Il runtime usa i criteri CAS legacy.|

### <a name="child-elements"></a>Elementi figlio

Nessuno.

### <a name="parent-elements"></a>Elementi padre

|Elemento|Descrizione|
|-------------|-----------------|
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|
|`runtime`|Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.|

## <a name="remarks"></a>Note

In .NET Framework versione 3,5 e versioni precedenti, i criteri CAS sono sempre attivi. Nella .NET Framework 4 è necessario abilitare i criteri CAS.

I criteri CAS sono specifici della versione. I criteri CAS personalizzati presenti nelle versioni precedenti del .NET Framework devono essere specificati nuovamente nell'.NET Framework 4.

L'applicazione `<NetFx40_LegacySecurityPolicy>` dell'elemento a un assembly .NET Framework 4 non influisce sul [codice SecurityTransparent](../../../misc/security-transparent-code.md); le regole di trasparenza sono comunque valide.

> [!IMPORTANT]
> L'applicazione `<NetFx40_LegacySecurityPolicy>` dell'elemento può comportare un calo significativo delle prestazioni per gli assembly di immagini native creati dal [Generatore di immagini native (Ngen. exe)](../../../tools/ngen-exe-native-image-generator.md) che non sono installati nel [global assembly cache](../../../app-domains/gac.md). Il calo delle prestazioni è dovuto al fatto che il runtime non è in grado di caricare gli assembly come immagini native quando viene applicato l'attributo, ottenendo così il caricamento come assembly JIT.

> [!NOTE]
> Se si specifica una versione di .NET Framework di destinazione precedente alla .NET Framework 4 nelle impostazioni del progetto per il progetto di Visual Studio, verranno abilitati i criteri CAS, inclusi i criteri CAS personalizzati specificati per tale versione. Tuttavia, non sarà possibile usare nuovi tipi e membri di .NET Framework 4. È anche possibile specificare una versione precedente del .NET Framework usando l' [ \<elemento > supportedRuntime](../startup/supportedruntime-element.md) nello schema delle impostazioni di avvio nel file di [configurazione dell'applicazione](../../index.md).

> [!NOTE]
> La sintassi del file di configurazione distingue tra maiuscole e minuscole. È necessario utilizzare la sintassi come indicato nelle sezioni Sintassi ed esempio.

## <a name="configuration-file"></a>File di configurazione

Questo elemento può essere utilizzato solo nel file di configurazione dell'applicazione.

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato come abilitare i criteri CAS legacy per un'applicazione.

```xml
<configuration>
   <runtime>
      <NetFx40_LegacySecurityPolicy enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a>Vedere anche

- [Schema delle impostazioni di runtime](index.md)
- [Schema dei file di configurazione](../index.md)
