---
title: <loadFromRemoteSources> Elemento
ms.date: 05/24/2018
helpviewer_keywords:
- loadFromRemoteSources element
- <loadFromRemoteSources> element
ms.assetid: 006d1280-2ac3-4db6-a984-a3d4e275046a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 83980d315c83aa5cc23944dbd271c29e0ed83206
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252471"
---
# <a name="loadfromremotesources-element"></a>\<elemento > loadFromRemoteSources
Specifica se agli assembly caricati da origini remote deve essere concessa l'attendibilità totale in .NET Framework 4 e versioni successive.
  
> [!NOTE]
> Se è stato indirizzato a questo articolo a causa di un messaggio di errore nell'elenco errori del progetto di Visual Studio o di [un errore di compilazione, vedere Procedura: Usare un assembly dal Web in Visual Studio](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee890038(v=vs.100)).  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> di runtime**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<> loadFromRemoteSources**  
  
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
|`enabled`|Attributo obbligatorio.<br /><br /> Specifica se a un assembly caricato da un'origine remota deve essere concessa l'attendibilità totale.|  
  
## <a name="enabled-attribute"></a>attributo enabled  
  
|Value|Descrizione|  
|-----------|-----------------|  
|`false`|Non concedere l'attendibilità totale alle applicazioni da origini remote. Questa è l'impostazione predefinita.|  
|`true`|Concedere l'attendibilità totale alle applicazioni dalle origini remote.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.|  
  
## <a name="remarks"></a>Note

In .NET Framework 3,5 e versioni precedenti, se si carica un assembly da una posizione remota, il codice nell'assembly viene eseguito in attendibilità parziale con un set di concessioni che dipende dalla zona da cui viene caricato. Ad esempio, se si carica un assembly da un sito Web, questo viene caricato nell'area Internet e viene concesso il set di autorizzazioni Internet. In altre parole, viene eseguito in una sandbox Internet.

A partire da .NET Framework 4, il criterio di sicurezza dall'accesso di codice (CAS) è disabilitato e gli assembly vengono caricati in attendibilità totale. In genere, in questo modo si concede l'attendibilità totale agli <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> assembly caricati con il metodo che in precedenza era stato creato mediante sandbox. Per evitare questo problema, la possibilità di eseguire il codice negli assembly caricati da un'origine remota è disabilitata per impostazione predefinita. Per impostazione predefinita, se si tenta di caricare un assembly remoto, <xref:System.IO.FileLoadException> viene generata un'eccezione con un messaggio di eccezione simile al seguente:

```text
System.IO.FileNotFoundException: Could not load file or assembly 'file:assem.dll' or one of its dependencies. Operation is not supported. 
(Exception from HRESULT: 0x80131515)
File name: 'file:assem.dll' ---> 
System.NotSupportedException: An attempt was made to load an assembly from a network location which would have caused the assembly 
to be sandboxed in previous versions of the .NET Framework. This release of the .NET Framework does not enable CAS policy by default, 
so this load may be dangerous. If this load is not intended to sandbox the assembly, please enable the loadFromRemoteSources switch. 
```

Per caricare l'assembly ed eseguire il codice, è necessario eseguire una delle operazioni seguenti:

- Creare in modo esplicito un sandbox per l'assembly [(vedere Procedura: Eseguire codice parzialmente attendibile in un](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)oggetto sandbox.

- Eseguire il codice dell'assembly in attendibilità totale. A tale scopo, configurare l' `<loadFromRemoteSources>` elemento. Consente di specificare che gli assembly eseguiti in attendibilità parziale nelle versioni precedenti del .NET Framework ora vengono eseguiti con attendibilità totale in .NET Framework 4 e versioni successive.

> [!IMPORTANT]
> Se l'assembly non deve essere eseguito con attendibilità totale, non impostare questo elemento di configurazione. <xref:System.AppDomain> In alternativa, creare un oggetto sandbox in cui caricare l'assembly.

L' `enabled` attributo per l' `<loadFromRemoteSources>` elemento è efficace solo quando la sicurezza dall'accesso di codice (CAS) è disabilitata. Per impostazione predefinita, il criterio CAS è disabilitato in .NET Framework 4 e versioni successive. Se si imposta `enabled` su `true`, agli assembly remoti viene concessa l'attendibilità totale.

Se `enabled` non è impostato su `true`, viene <xref:System.IO.FileLoadException> generata un'eccezione in una delle condizioni seguenti:

- Il comportamento di sandboxing del dominio corrente è diverso dal relativo comportamento nella .NET Framework 3,5. Questa operazione richiede che i criteri CAS siano disabilitati e che il dominio corrente non venga creato mediante sandbox.

- L'assembly da caricare non è dalla `MyComputer` zona.

L'impostazione `<loadFromRemoteSources>` dell'elemento `true` su impedisce che venga generata questa eccezione. Consente di specificare che non si basano sulla Common Language Runtime per eseguire la sandbox degli assembly caricati per la sicurezza e che è possibile eseguirli con attendibilità totale.

## <a name="notes"></a>Note

- In .NET Framework 4,5 e versioni successive, gli assembly sulle condivisioni di rete locali vengono eseguiti in attendibilità totale per impostazione predefinita. non è necessario abilitare l' `<loadFromRemoteSources>` elemento.

- Se un'applicazione è stata copiata dal Web, viene contrassegnata da Windows come applicazione Web, anche se risiede nel computer locale. È possibile modificare la designazione cambiando le proprietà del file oppure è possibile utilizzare l' `<loadFromRemoteSources>` elemento per concedere l'attendibilità totale dell'assembly. In alternativa, è possibile usare il <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> metodo per caricare un assembly locale segnalato dal sistema operativo come caricato dal Web.

- È possibile ottenere un <xref:System.IO.FileLoadException> oggetto in un'applicazione in esecuzione in un'applicazione Windows Virtual PC. Questo problema può verificarsi quando si tenta di caricare un file dalle cartelle collegate nel computer host. Può inoltre verificarsi quando si tenta di caricare un file da una cartella collegata tramite [Servizi Desktop remoto](https://go.microsoft.com/fwlink/?LinkId=182775) (Servizi terminal). Per evitare l'eccezione, impostare `enabled` su `true`.

## <a name="configuration-file"></a>File di configurazione

Questo elemento viene in genere usato nel file di configurazione dell'applicazione, ma può essere usato in altri file di configurazione a seconda del contesto. Per ulteriori informazioni, vedere l'articolo [utilizzi più impliciti dei criteri CAS: loadFromRemoteSources](https://go.microsoft.com/fwlink/p/?LinkId=266839) nel Blog sulla sicurezza di .NET.  

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato come concedere l'attendibilità totale agli assembly caricati da origini remote.

```xml
<configuration>  
   <runtime>  
      <loadFromRemoteSources enabled="true"/>  
   </runtime>  
</configuration>  
```

## <a name="see-also"></a>Vedere anche

- [Utilizzi più impliciti dei criteri CAS: loadFromRemoteSources](https://go.microsoft.com/fwlink/p/?LinkId=266839)
- [Procedura: Eseguire codice parzialmente attendibile in un oggetto sandbox](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)
- [Schema delle impostazioni di runtime](index.md)
- [Schema dei file di configurazione](../index.md)
- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>
