---
title: <loadFromRemoteSources> Elemento
ms.date: 05/24/2018
helpviewer_keywords:
- loadFromRemoteSources element
- <loadFromRemoteSources> element
ms.assetid: 006d1280-2ac3-4db6-a984-a3d4e275046a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7568129f30267b212737ec8aa688cf882e19bbff
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704596"
---
# <a name="loadfromremotesources-element"></a>\<loadFromRemoteSources > elemento
Specifica se gli assembly caricati da origini remote devono essere concessa l'attendibilità in .NET Framework 4 e versioni successive.
  
> [!NOTE]
>  Se si viene reindirizzati a questo articolo a causa di un messaggio di errore nell'elenco di errori di progetto Visual Studio o un errore di compilazione, vedere [come: Usare un Assembly dal Web in Visual Studio](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee890038(v=vs.100)).  
  
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
|`enabled`|Attributo obbligatorio.<br /><br /> Specifica se un assembly caricato da un'origine remota deve essere concessa attendibilità totale.|  
  
## <a name="enabled-attribute"></a>attributo Enabled  
  
|Value|Descrizione|  
|-----------|-----------------|  
|`false`|Non concedere l'attendibilità totale alle applicazioni da origini remote. Questa è l'impostazione predefinita.|  
|`true`|Concedere l'attendibilità totale alle applicazioni da origini remote.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.|  
  
## <a name="remarks"></a>Note

In .NET Framework 3.5 e versioni precedenti, se si carica un assembly da una posizione remota, il codice nell'assembly viene eseguito in attendibilità parziale con un set di concessioni che varia a seconda della zona da cui viene caricato. Ad esempio, se si carica un assembly da un sito Web, viene caricato nella zona Internet e concesso il set di autorizzazioni Internet. In altre parole, viene eseguito in una sandbox di Internet.

A partire da .NET Framework 4, criteri di sicurezza dall'accesso di codice sono disabilitato e gli assembly vengono caricati con attendibilità totale. In genere, ciò potrebbe concedere l'attendibilità per gli assembly caricati con il <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> metodo che in precedenza era stato creato mediante sandbox. Per evitare questo problema, la possibilità di eseguire il codice negli assembly caricati da un'origine remota è disabilitata per impostazione predefinita. Per impostazione predefinita, se si tenta di caricare un assembly remoto, un <xref:System.IO.FileLoadException> con un messaggio di eccezione, ad esempio, viene generata la seguente:

```text
System.IO.FileNotFoundException: Could not load file or assembly 'file:assem.dll' or one of its dependencies. Operation is not supported. 
(Exception from HRESULT: 0x80131515)
File name: 'file:assem.dll' ---> 
System.NotSupportedException: An attempt was made to load an assembly from a network location which would have caused the assembly 
to be sandboxed in previous versions of the .NET Framework. This release of the .NET Framework does not enable CAS policy by default, 
so this load may be dangerous. If this load is not intended to sandbox the assembly, please enable the loadFromRemoteSources switch. 
```

Per caricare l'assembly ed eseguire il codice, è necessario:

- Creare in modo esplicito un ambiente sandbox per l'assembly (vedere [come: Eseguire codice parzialmente attendibile in un ambiente Sandbox](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)).

- Eseguire il codice dell'assembly con attendibilità totale. A tale scopo, la configurazione di `<loadFromRemoteSources>` elemento. Consente di specificare che gli assembly eseguiti in attendibilità parziale in versioni precedenti di .NET Framework ora eseguito con attendibilità totale in .NET Framework 4 e versioni successive.

> [!IMPORTANT]
> Se l'assembly non deve essere eseguito con attendibilità totale, non impostare questo elemento di configurazione. In alternativa, creare un sandbox <xref:System.AppDomain> in cui caricare l'assembly.

Il `enabled` dell'attributo per il `<loadFromRemoteSources>` elemento è efficace solo quando è disabilitato sicurezza dall'accesso di codice (CAS). Per impostazione predefinita, tali criteri sono disabilitati in .NET Framework 4 e versioni successive. Se si imposta `enabled` a `true`, agli assembly remoti viene concessa l'attendibilità totale.

Se `enabled` non è impostata su `true`, un <xref:System.IO.FileLoadException> viene generata in presenza delle condizioni seguenti:

- Il comportamento di sandboxing del dominio corrente è diverso dal comportamento in .NET Framework 3.5. Ciò richiede criteri CAS deve essere disabilitata e il dominio corrente non deve essere creata mediante sandbox.

- Il caricamento dell'assembly non proviene dal `MyComputer` zona.

Impostando il `<loadFromRemoteSources>` elemento `true` impedisce che venga generata questa eccezione. Consente di specificare che non fare affidamento sul common language runtime a sandbox gli assembly caricati per la sicurezza e che può essere autorizzato per l'esecuzione in attendibilità totale.

## <a name="notes"></a>Note

- In .NET Framework 4.5 e versioni successive, assembly nelle condivisioni di rete locale vengono eseguiti con attendibilità totale per impostazione predefinita. non è necessario abilitare il `<loadFromRemoteSources>` elemento.

- Se un'applicazione è stata copiata dal web, questa viene contrassegnata da Windows come un'applicazione web, anche se si trova nel computer locale. È possibile modificare tale designazione modificandone le proprietà di file, oppure è possibile usare il `<loadFromRemoteSources>` elemento da concedere all'assembly con attendibilità totale. In alternativa, è possibile usare il <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> per caricare un assembly locale che il sistema operativo ha contrassegnato come se fosse stato caricato dal web.

- È possibile che venga visualizzato un <xref:System.IO.FileLoadException> in un'applicazione in esecuzione in un'applicazione Windows Virtual PC. Questa situazione può verificarsi quando si prova a caricare un file da cartelle collegate al computer host. Può verificarsi anche quando si prova a caricare un file da una cartella collegata a [Servizi Desktop remoto](https://go.microsoft.com/fwlink/?LinkId=182775) (servizi Terminal). Per evitare l'eccezione, impostare `enabled` a `true`.

## <a name="configuration-file"></a>File di configurazione

Questo elemento viene in genere usato nel file di configurazione dell'applicazione, ma può essere usato in altri file di configurazione a seconda del contesto. Per altre informazioni, vedere l'articolo [altre implicita Usa del criterio CAS: loadFromRemoteSources](https://go.microsoft.com/fwlink/p/?LinkId=266839) nel blog .NET Security.  

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato come concedere l'attendibilità totale per gli assembly caricati da origini remote.

```xml
<configuration>  
   <runtime>  
      <loadFromRemoteSources enabled="true"/>  
   </runtime>  
</configuration>  
```

## <a name="see-also"></a>Vedere anche

- [Utilizzi più impliciti dei criteri CAS: loadFromRemoteSources](https://go.microsoft.com/fwlink/p/?LinkId=266839)
- [Procedura: Eseguire codice parzialmente attendibile in un oggetto sandbox](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)
- [Schema delle impostazioni di runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Schema dei file di configurazione](../../../../../docs/framework/configure-apps/file-schema/index.md)
- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>
