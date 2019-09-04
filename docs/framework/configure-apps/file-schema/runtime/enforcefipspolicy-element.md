---
title: <enforceFIPSPolicy> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- enforceFIPSPolicy element
- FIPS
- <enforceFIPSPolicy> element
- Federal Information Processing Standards (FIPS)
ms.assetid: c35509c4-35cf-43c0-bb47-75e4208aa24e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f90abf9f6c2bc0aed2cf01558b2c0cca4e967e81
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252640"
---
# <a name="enforcefipspolicy-element"></a>\<Elemento > enforceFIPSPolicy
Specifica se applicare un requisito di configurazione del computer che specifica che gli algoritmi di crittografia devono essere conformi a FIPS (Federal Information Processing Standards).  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> di runtime**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<enforceFIPSPolicy>**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<enforceFIPSPolicy enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|enabled|Attributo obbligatorio.<br /><br /> Specifica se consentire l'applicazione di un requisito di configurazione del computer che gli algoritmi di crittografia devono essere conformi a FIPS.|  
  
## <a name="enabled-attribute"></a>Attributo enabled  
  
|Valore|DESCRIZIONE|  
|-----------|-----------------|  
|`true`|Se il computer è configurato per richiedere che gli algoritmi di crittografia siano conformi a FIPS, il requisito viene applicato. Se una classe implementa un algoritmo non conforme a FIPS, i costruttori o `Create` i metodi di tale classe generano eccezioni quando vengono eseguiti nel computer. Questa è l'impostazione predefinita.|  
|`false`|Gli algoritmi di crittografia utilizzati dall'applicazione non devono essere conformi a FIPS, indipendentemente dalla configurazione del computer.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|  
  
## <a name="remarks"></a>Note  
 A partire da .NET Framework 2,0, la creazione di classi che implementano algoritmi di crittografia è controllata dalla configurazione del computer. Se il computer è configurato per richiedere che gli algoritmi siano conformi a FIPS e una classe implementa un algoritmo non conforme a FIPS, qualsiasi tentativo di creare un'istanza di tale classe genererà un'eccezione. I costruttori generano <xref:System.InvalidOperationException> un'eccezione e `Create` i metodi generano <xref:System.Reflection.TargetInvocationException> un'eccezione con <xref:System.InvalidOperationException> un'eccezione interna.  
  
 Se l'applicazione viene eseguita su computer le cui configurazioni richiedono la conformità con FIPS e l'applicazione utilizza un algoritmo non conforme a FIPS, è possibile utilizzare questo elemento nel file di configurazione per impedire che il Common Language Runtime (CLR) da applicazione della conformità FIPS. Questo elemento è stato introdotto in .NET Framework 2,0 Service Pack 1.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come impedire a CLR di applicare la conformità FIPS.  
  
```xml  
<configuration>  
    <runtime>  
        <enforceFIPSPolicy enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Schema delle impostazioni di runtime](index.md)
- [Schema dei file di configurazione](../index.md)
- [Modello di crittografia](../../../../standard/security/cryptography-model.md)
