---
title: '&lt;loadFromRemoteSources&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- loadFromRemoteSources element
- <loadFromRemoteSources> element
ms.assetid: 006d1280-2ac3-4db6-a984-a3d4e275046a
caps.latest.revision: "31"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 13b42405a0faf721c46476aadaa0cff8163883c1
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="ltloadfromremotesourcesgt-element"></a>&lt;loadFromRemoteSources&gt; elemento
Specifica se gli assembly da origini remote devono essere concesso l'attendibilità totale.  
  
> [!NOTE]
>  Se si viene indirizzati a questo argomento, a causa di un messaggio di errore nell'elenco di errori di progetto Visual Studio o un errore di compilazione, vedere [procedura: utilizzare un Assembly dal Web in Visual Studio](http://msdn.microsoft.com/library/d8635b63-89a0-41aa-90f4-f351b2111070).  
  
 \<configuration>  
\<runtime>  
\<loadFromRemoteSources>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<loadFromRemoteSources    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`enabled`|Attributo obbligatorio.<br /><br /> Specifica se un assembly caricato da origini remote deve essere concessa l'attendibilità totale.|  
  
## <a name="enabled-attribute"></a>Attributo enabled  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|`false`|Non concedere l'attendibilità totale alle applicazioni provenienti da origini remote. Questa è l'impostazione predefinita.|  
|`true`|Concedere l'attendibilità totale alle applicazioni provenienti da origini remote.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.|  
  
## <a name="remarks"></a>Note  
 In .NET Framework versione 3.5 e versioni precedenti, se un assembly caricato da una posizione remota, l'assembly parzialmente attendibile con un set di concessioni che dipende dalla zona in cui è stato caricato. Ad esempio, se un assembly caricato da un sito Web, è stato caricato nella zona Internet e concesso il set di autorizzazioni Internet. In altre parole, eseguita in un ambiente sandbox Internet. Se si tenta di eseguire tale assembly nel [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] e versioni successive, viene generata un'eccezione; è necessario creare esplicitamente una sandbox per l'assembly (vedere [procedura: eseguire codice parzialmente attendibile in un ambiente Sandbox](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)), oppure eseguirlo con attendibilità totale.  
  
 Il `<loadFromRemoteSources>` elemento consente specificare che devono essere eseguiti gli assembly che si sarebbero verificati parzialmente attendibile in versioni precedenti di .NET Framework con attendibilità totale nel [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] e versioni successive. Per impostazione predefinita, assembly remoti a non eseguire il [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] e versioni successive. Per eseguire un assembly remoto, è necessario eseguirla come completamente attendibile o creare una sandbox <xref:System.AppDomain> in cui si desidera eseguirlo.  
  
> [!NOTE]
>  Nel [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)], gli assembly nelle condivisioni di rete locale vengono eseguiti con attendibilità totale per impostazione predefinita; non è necessario abilitare il `<loadFromRemoteSources>` elemento.  
  
> [!NOTE]
>  Se un'applicazione è stata copiata dal web, questa viene contrassegnata da Windows come un'applicazione web, anche se si trova nel computer locale. È possibile modificare tale designazione modificando le proprietà del file, oppure è possibile utilizzare il `<loadFromRemoteSources>` elemento da concedere all'assembly con attendibilità totale. In alternativa, è possibile utilizzare il <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> per caricare un assembly locale che il sistema operativo è contrassegnato come se fosse stato caricato dal web.  
  
 Il `enabled` attributo per questo elemento è efficace solo quando sicurezza dall'accesso di codice (CAS) è disabilitato. Per impostazione predefinita, le autorità di certificazione è disattivato nel [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] e versioni successive. Se si imposta `enabled` a `true`, le applicazioni remote vengono concessa l'attendibilità.  
  
 Se `<loadFromRemoteSources>``enabled` non è impostata su `true`, viene generata un'eccezione nelle condizioni seguenti:  
  
-   Il comportamento di sandboxing del dominio corrente è diverso dal comportamento nel [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)]. Sono necessari criteri Autorità di certificazione deve essere disabilitata e il dominio corrente non deve essere creata mediante sandbox.  
  
-   Il caricamento dell'assembly non è il `MyComputer` zona.  
  
> [!NOTE]
>  È possibile ottenere un <xref:System.IO.FileLoadException> in un'applicazione Windows Virtual PC quando si tenta di caricare un file dalle cartelle collegate sul computer host. Questo errore può verificarsi anche quando si tenta di caricare un file da una cartella collegata tramite [Servizi Desktop remoto](http://go.microsoft.com/fwlink/?LinkId=182775) (servizi Terminal). Per evitare l'eccezione, impostare `enabled` a `true`.  
  
 L'impostazione di `<loadFromRemoteSources>` elemento `true` impedisce che venga generata questa eccezione. Consente di specificare che non si in common language runtime per la sandbox gli assembly caricati per la sicurezza e che può concedere l'esecuzione con attendibilità totale.  
  
> [!IMPORTANT]
>  Se l'assembly non deve essere eseguito con attendibilità totale, non impostare questo elemento di configurazione. In alternativa, creare una sandbox <xref:System.AppDomain> in cui caricare l'assembly.  
  
## <a name="configuration-file"></a>File di configurazione  
 Questo elemento viene in genere utilizzato nel file di configurazione dell'applicazione, ma può essere utilizzato in altri file di configurazione in base al contesto. Per ulteriori informazioni, vedere l'articolo [più implicita Usa di questi criteri: loadFromRemoteSources](http://go.microsoft.com/fwlink/p/?LinkId=266839) nel blog di sicurezza di .NET.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come concedere l'attendibilità totale alle applicazioni provenienti da origini remote.  
  
```xml  
<configuration>  
   <runtime>  
      <loadFromRemoteSources enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Più impliciti utilizzi di questi criteri: loadFromRemoteSources](http://go.microsoft.com/fwlink/p/?LinkId=266839)  
 [Procedura: eseguire codice parzialmente attendibile in un oggetto sandbox](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)  
 [Schema delle impostazioni di runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Schema dei file di configurazione](../../../../../docs/framework/configure-apps/file-schema/index.md)
