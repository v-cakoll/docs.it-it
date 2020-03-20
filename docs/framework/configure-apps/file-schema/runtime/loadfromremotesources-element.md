---
title: <loadFromRemoteSources> Elemento
ms.date: 05/24/2018
helpviewer_keywords:
- loadFromRemoteSources element
- <loadFromRemoteSources> element
ms.assetid: 006d1280-2ac3-4db6-a984-a3d4e275046a
ms.openlocfilehash: a0dcffe378cdd09de0fbd8f0a6ef0635c033fd9c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154062"
---
# <a name="loadfromremotesources-element"></a>\<elemento> loadFromRemoteSources
Specifica se agli assembly caricati da origini remote deve essere concessa l'attendibilità totale in .NET Framework 4 e versioni successive.
  
> [!NOTE]
> Se si è stati indirizzati a questo articolo a causa di un messaggio di errore nell'elenco degli errori del progetto di Visual Studio o di un errore di compilazione, vedere [procedura: utilizzare un assembly dal Web in Visual Studio](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee890038(v=vs.100)).  
  
[**\<>di configurazione**](../configuration-element.md)\
&nbsp;&nbsp;[**\<>di runtime**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<>loadFromRemoteSources**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<loadFromRemoteSources
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributes  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`enabled`|Attributo obbligatorio.<br /><br /> Specifica se a un assembly caricato da un'origine remota deve essere concessa l'attendibilità totale.|  
  
## <a name="enabled-attribute"></a>attributo enabled  
  
|valore|Descrizione|  
|-----------|-----------------|  
|`false`|Non concedere l'attendibilità totale alle applicazioni provenienti da origini remote. Questa è la modalità predefinita.|  
|`true`|Concedere l'attendibilità totale alle applicazioni da origini remote.|  
  
### <a name="child-elements"></a>Elementi figlio  
 No.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.|  
  
## <a name="remarks"></a>Osservazioni

In .NET Framework 3.5 e versioni precedenti, se si carica un assembly da una posizione remota, il codice nell'assembly viene eseguito in attendibilità parziale con un set di concessioni che dipende dalla zona da cui viene caricato. Ad esempio, se si carica un assembly da un sito Web, questo viene caricato nell'area Internet e viene concesso il set di autorizzazioni Internet. In altre parole, viene eseguito in una sandbox Internet.

A partire da .NET Framework 4.NET Framework 4, i criteri di sicurezza dall'accesso di codice sono disabilitati e gli assembly vengono caricati con attendibilità totale. In genere, ciò concedelrebbe l'attendibilità totale agli assembly caricati con il <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> metodo che in precedenza era stato sottoposto a sandbox. Per evitare questo problema, la possibilità di eseguire codice negli assembly caricati da un'origine remota è disabilitata per impostazione predefinita. Per impostazione predefinita, se si tenta <xref:System.IO.FileLoadException> di caricare un assembly remoto, viene generato un messaggio di eccezione simile al seguente:

```text
System.IO.FileNotFoundException: Could not load file or assembly 'file:assem.dll' or one of its dependencies. Operation is not supported.
(Exception from HRESULT: 0x80131515)
File name: 'file:assem.dll' --->
System.NotSupportedException: An attempt was made to load an assembly from a network location which would have caused the assembly
to be sandboxed in previous versions of the .NET Framework. This release of the .NET Framework does not enable CAS policy by default,
so this load may be dangerous. If this load is not intended to sandbox the assembly, please enable the loadFromRemoteSources switch.
```

Per caricare l'assembly ed eseguirne il codice, è necessario:

- Creare in modo esplicito una sandbox per l'assembly (vedere [Procedura: eseguire codice parzialmente attendibile in una sandbox](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)).

- Eseguire il codice dell'assembly con attendibilità totale. A tale scopo, `<loadFromRemoteSources>` configurare l'elemento. Consente di specificare che gli assembly eseguiti in attendibilità parziale nelle versioni precedenti di .NET Framework vengono ora eseguiti in attendibilità totale in .NET Framework 4 e versioni successive.

> [!IMPORTANT]
> Se l'assembly non deve essere eseguito con attendibilità totale, non impostare questo elemento di configurazione. Creare invece una <xref:System.AppDomain> sandbox in cui caricare l'assieme.

`enabled` L'attributo `<loadFromRemoteSources>` per l'elemento è valido solo quando la sicurezza dall'accesso di codice (CAS) è disabilitata. Per impostazione predefinita, i criteri CAS sono disabilitati in .NET Framework 4 e versioni successive. Se si `enabled` `true`imposta su , agli assembly remoti viene concessa l'attendibilità totale.

Se `enabled` non è `true`impostato <xref:System.IO.FileLoadException> su , viene generata una eccezione in una delle seguenti condizioni:

- Il comportamento sandbox del dominio corrente è diverso dal comportamento in .NET Framework 3.5. Ciò richiede la disabilitazione dei criteri CAS e il dominio corrente non deve essere inmodale.

- L'assembly caricato non `MyComputer` proviene dalla zona.

L'impostazione `true` dell'elemento su impedisce la `<loadFromRemoteSources>` creazione di questa eccezione. Consente di specificare che non si basa su Common Language Runtime per inserire in modalità sandbox gli assembly caricati per la sicurezza e che possono essere autorizzati a eseguire in attendibilità totale.

## <a name="notes"></a>Note

- In .NET Framework 4.5 e versioni successive, gli assembly nelle condivisioni di rete locali vengono eseguiti con attendibilità totale per impostazione predefinita. non è necessario abilitare l'elemento. `<loadFromRemoteSources>`

- Se un'applicazione è stata copiata dal Web, viene contrassegnata da Windows come applicazione Web, anche se risiede nel computer locale. È possibile modificare tale designazione modificandone le proprietà `<loadFromRemoteSources>` del file oppure utilizzare l'elemento per concedere all'assembly l'attendibilità totale. In alternativa, è possibile <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> utilizzare il metodo per caricare un assembly locale contrassegnato come caricato dal Web.

- È possibile <xref:System.IO.FileLoadException> ottenere un in un'applicazione in esecuzione in un'applicazione Windows Virtual PC. Ciò può verificarsi quando si tenta di caricare un file da cartelle collegate sul computer host. Può verificarsi anche quando si tenta di caricare un file da una cartella collegata tramite [Servizi Desktop remoto](/windows/win32/termserv/terminal-services-portal) (Servizi terminal). Per evitare l'eccezione, impostare `enabled` su `true`.

## <a name="configuration-file"></a>File di configurazione

Questo elemento viene in genere utilizzato nel file di configurazione dell'applicazione, ma può essere utilizzato in altri file di configurazione a seconda del contesto. Per altre informazioni, vedere l'articolo [Altri utilizzi impliciti di Criteri CA: loadFromRemoteSources](https://docs.microsoft.com/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources) nel blog sulla sicurezza di .NET.  

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

- [Usi più impliciti dei criteri CAS: loadFromRemoteSources](https://docs.microsoft.com/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources)
- [Procedura: eseguire codice parzialmente attendibile in un oggetto sandbox](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)
- [Schema delle impostazioni di runtime](index.md)
- [Schema del file di configurazione](../index.md)
- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>
