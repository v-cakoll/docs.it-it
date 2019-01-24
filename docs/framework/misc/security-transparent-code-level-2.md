---
title: Codice SecurityTransparent, livello 2
ms.date: 03/30/2017
helpviewer_keywords:
- transparency
- level 2 transparency
- security-transparent code
- security-critical code
ms.assetid: 4d05610a-0da6-4f08-acea-d54c9d6143c0
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8425b294328d4fc7546a372b329d8fa834a088d6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54567022"
---
# <a name="security-transparent-code-level-2"></a>Codice SecurityTransparent, livello 2
<a name="top"></a>
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 La trasparenza di livello 2 è stata introdotta in [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]. I tre concetti principali di questo modello sono il codice Transparent, il codice SecuritySafeCritical e il codice SecurityCritical.  
  
-   Il codice Transparent, incluso il codice in esecuzione con attendibilità totale, può chiamare solo altro codice Transparent o codice SecuritySafeCritical. Può eseguire solo azioni consentite dal set di autorizzazioni parzialmente attendibile, se esistente, del dominio. Il codice Transparent non può eseguire le operazioni seguenti:  
  
    -   Eseguire un metodo <xref:System.Security.CodeAccessPermission.Assert%2A> o un'elevazione dei privilegi.  
  
    -   Contenere codice di tipo unsafe o non verificabile.  
  
    -   Chiamare direttamente codice Critical.  
  
    -   Chiamare codice nativo o codice con l'attributo <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute>.  
  
    -   Chiamare un membro protetto da <xref:System.Security.Permissions.SecurityAction.LinkDemand>.  
  
    -   Ereditare dai tipi Critical.  
  
     Inoltre, i metodi Transparent non possono eseguire l'override di metodi virtuali Critical o implementare metodi di interfaccia Critical.  
  
-   Il codice SafeCritical è completamente attendibile, ma può essere chiamato dal codice Transparent. Espone una superficie di attacco limitata di codice con attendibilità totale; nel codice SafeCritical vengono eseguite verifiche della correttezza e della sicurezza.  
  
-   Il codice SecurityCritical può chiamare qualsiasi tipo di codice ed è completamente attendibile, ma non può essere chiamato da codice Transparent.  
  
 Di seguito sono elencate le diverse sezioni di questo argomento:  
  
-   [Esempi di utilizzo e i comportamenti](#examples)  
  
-   [Criteri di override](#override)  
  
-   [Regole di ereditarietà](#inheritance)  
  
-   [Le regole e informazioni aggiuntive](#additional)  
  
<a name="examples"></a>   
## <a name="usage-examples-and-behaviors"></a>Esempi di utilizzo e comportamenti  
 Per specificare le regole di [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] (trasparenza di livello 2), usare l'annotazione seguente per un assembly:  
  
```  
[assembly: SecurityRules(SecurityRuleSet.Level2)]  
```  
  
 Per usare le regole di .NET Framework 2.0 (trasparenza di livello 1), usare l'annotazione seguente:  
  
```  
[assembly: SecurityRules(SecurityRuleSet.Level1)]  
```  
  
 Se non si annota un assembly, per impostazione predefinita vengono usate le regole di [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]. Tuttavia, la procedura consigliata consiste nell'utilizzare il <xref:System.Security.SecurityRulesAttribute> attributo anziché in base il valore predefinito.  
  
### <a name="assembly-wide-annotation"></a>Annotazione a livello di assembly  
 Le regole seguenti si applicano all'uso degli attributi a livello di assembly.  
  
-   Non sono presenti attributi: Se non si specifica qualsiasi attributo, il runtime interpreta tutto il codice come SecurityCritical, tranne dove essere SecurityCritical viola una regola di ereditarietà (ad esempio, quando si esegue l'override o implementando un trasparente metodo di interfaccia o virtuale). In tali casi, i metodi sono SafeCritical. Se non si specificano attributi, Common Language Runtime determina automaticamente le regole di trasparenza.  
  
-   `SecurityTransparent`: Tutto il codice è transparent; l'intero assembly non eseguirà operazioni con privilegi o unsafe.  
  
-   `SecurityCritical`: Tutto il codice introdotto dai tipi di questo assembly è Critical, mentre tutto l'altro codice è Transparent. Questo scenario è simile al caso in cui non vengono specificati attributi. Tuttavia Common Language Runtime non determina automaticamente le regole di trasparenza. Se si esegue ad esempio l'override di un metodo virtuale o astratto oppure si implementa un metodo di interfaccia, per impostazione predefinita tale metodo è Transparent. È necessario annotare in modo esplicito il metodo come `SecurityCritical` o `SecuritySafeCritical`; in caso contrario, verrà generata un'eccezione <xref:System.TypeLoadException> durante il caricamento. Questa regola si applica anche quando la classe base e la classe derivata si trovano nello stesso assembly.  
  
-   `AllowPartiallyTrustedCallers` (solo a livello 2): Tutto il codice è Transparent per impostazione predefinita. I singoli tipi e membri possono tuttavia avere altri attributi.  
  
 Nella tabella seguente confronta il comportamento a livello di assembly per il livello 2 con livello 1.  
  
|Assembly (attributo)|Livello 2|Livello 1|  
|------------------------|-------------|-------------|  
|Nessun attributo su un assembly parzialmente attendibile|I tipi e i membri sono Transparent per impostazione predefinita, ma possono essere SecurityCritical o SecuritySafeCritical.|Tutti i tipi e i membri sono Transparent.|  
|Nessun attributo|Se non si specificano attributi, Common Language Runtime determina automaticamente le regole di trasparenza. Tutti i tipi e i membri sono SecurityCritical, tranne nei casi in cui tale caratteristica viola una regola di ereditarietà.|In un assembly completamente attendibile (nella Global Assembly Cache o identificato come con attendibilità totale in `AppDomain`) tutti i tipi sono Transparent e tutti i membri sono SecuritySafeCritical.|  
|`SecurityTransparent`|Tutti i tipi e i membri sono Transparent.|Tutti i tipi e i membri sono Transparent.|  
|`SecurityCritical(SecurityCriticalScope.Everything)`|Non applicabile.|Tutti i tipi e i membri sono SecurityCritical.|  
|`SecurityCritical`|Tutto il codice introdotto dai tipi di questo assembly è Critical, mentre tutto l'altro codice è Transparent. Se si esegue l'override di un metodo virtuale o astratto oppure si implementa un metodo di interfaccia, è necessario annotare in modo esplicito il metodo come `SecurityCritical` o `SecuritySafeCritical`.|Tutto il codice è Transparent per impostazione predefinita. I singoli tipi e membri possono tuttavia avere altri attributi.|  
  
### <a name="type-and-member-annotation"></a>Annotazione dei tipi e dei membri  
 Gli attributi di sicurezza applicati a un tipo si applicano anche ai membri introdotti dal tipo. Non si applicano tuttavia a override virtuali o astratti della classe base o delle implementazioni dell'interfaccia. Le regole seguenti si applicano all'uso degli attributi a livello di tipo e membro:  
  
-   `SecurityCritical`: Il tipo o membro è critico e può essere chiamato solo da codice completamente attendibile. I metodi introdotti in un tipo SecurityCritical sono Critical.  
  
    > [!IMPORTANT]
    >  I metodi virtuali e astratti introdotti in classi base o interfacce e sottoposti a override o implementati in una classe SecurityCritical sono Transparent per impostazione predefinita. Devono essere identificati come `SecuritySafeCritical` o `SecurityCritical`.  
  
-   `SecuritySafeCritical`: Il tipo o membro è SafeCritical. Il tipo o il membro può tuttavia essere chiamato da codice Transparent (parzialmente attendibile) e funziona come qualsiasi altro codice Critical. Il codice deve essere controllato per garantirne la sicurezza.  
  
 [Torna all'inizio](#top)  
  
<a name="override"></a>   
## <a name="override-patterns"></a>Criteri di override  
 Nella tabella seguente vengono elencati gli override dei metodi consentiti per la trasparenza di livello 2.  
  
|Membro di base virtuale/di interfaccia|Override/interfaccia|  
|------------------------------------|-------------------------|  
|`Transparent`|`Transparent`|  
|`Transparent`|`SafeCritical`|  
|`SafeCritical`|`Transparent`|  
|`SafeCritical`|`SafeCritical`|  
|`Critical`|`Critical`|  
  
 [Torna all'inizio](#top)  
  
<a name="inheritance"></a>   
## <a name="inheritance-rules"></a>Regole di ereditarietà  
 In questa sezione, l'ordine seguente è assegnato al codice `Transparent`, `Critical` e `SafeCritical` in base all'accesso e alle funzionalità:   
  
 `Transparent` < `SafeCritical` < `Critical`  
  
-   Regole per i tipi: Procedendo da sinistra verso destra, l'accesso diventa più restrittivo. I tipi derivati devono essere restrittivi almeno quanto il tipo di base.  
  
-   Regole per i metodi: I metodi derivati non è possibile modificare l'accessibilità dal metodo base. Per il comportamento predefinito, tutti i metodi derivati non annotati sono `Transparent`. I derivati di tipi Critical provocano un'eccezione se il metodo sottoposto a override non è annotato in modo esplicito come `SecurityCritical`.  
  
 Nella tabella seguente vengono elencati i criteri dell'ereditarietà dei tipi consentiti.  
  
|Classe base|La classe derivata può essere|  
|----------------|--------------------------|  
|`Transparent`|`Transparent`|  
|`Transparent`|`SafeCritical`|  
|`Transparent`|`Critical`|  
|`SafeCritical`|`SafeCritical`|  
|`SafeCritical`|`Critical`|  
|`Critical`|`Critical`|  
  
 Nella tabella seguente vengono elencati i criteri di ereditarietà dei tipi non consentiti.  
  
|Classe base|La classe derivata non può essere|  
|----------------|-----------------------------|  
|`SafeCritical`|`Transparent`|  
|`Critical`|`Transparent`|  
|`Critical`|`SafeCritical`|  
  
 Nella tabella seguente vengono elencati i criteri di ereditarietà dei metodi consentiti.  
  
|Metodo di base|Il metodo derivato può essere|  
|-----------------|---------------------------|  
|`Transparent`|`Transparent`|  
|`Transparent`|`SafeCritical`|  
|`SafeCritical`|`Transparent`|  
|`SafeCritical`|`SafeCritical`|  
|`Critical`|`Critical`|  
  
 Nella tabella seguente vengono elencati i criteri di ereditarietà dei metodi non consentiti.  
  
|Metodo di base|Il metodo derivato non può essere|  
|-----------------|------------------------------|  
|`Transparent`|`Critical`|  
|`SafeCritical`|`Critical`|  
|`Critical`|`Transparent`|  
|`Critical`|`SafeCritical`|  
  
> [!NOTE]
>  Queste regole di ereditarietà si applicano a tipi e membri di livello 2. I tipi di assembly di livello 1 possono ereditare dai membri e dai tipi SecurityCritical di livello 2. Pertanto, i tipi e i membri di livello 2 devono disporre di richieste di ereditarietà separate per gli eredi di livello 1.  
  
 [Torna all'inizio](#top)  
  
<a name="additional"></a>   
## <a name="additional-information-and-rules"></a>Informazioni e regole aggiuntive  
  
### <a name="linkdemand-support"></a>Supporto LinkDemand  
 Nel modello di trasparenza di livello 2, <xref:System.Security.Permissions.SecurityAction.LinkDemand> è stato sostituito dall'attributo <xref:System.Security.SecurityCriticalAttribute>. Nel codice legacy (livello 1), <xref:System.Security.Permissions.SecurityAction.LinkDemand> viene trattato automaticamente come <xref:System.Security.Permissions.SecurityAction.Demand>.  
  
### <a name="reflection"></a>Reflection  
 Se si richiama un metodo Critical o si legge un campo Critical, viene generata una richiesta di attendibilità totale, come se si stesse richiamando un metodo o un campo Private. Il codice con attendibilità totale può quindi richiamare un metodo Critical, a differenza del codice parzialmente attendibile.  
  
 Le proprietà seguenti sono state aggiunte allo spazio dei nomi di <xref:System.Reflection> per determinare se il tipo, il metodo, o il campo è `SecurityCritical`, `SecuritySafeCritical` o `SecurityTransparent`: <xref:System.Type.IsSecurityCritical%2A>, <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A> e <xref:System.Reflection.MethodBase.IsSecurityTransparent%2A>. Usare queste proprietà per determinare la trasparenza con reflection anziché verificare la presenza dell'attributo. Le regole di trasparenza sono complesse ed la verifica dell'attributo potrebbe non essere sufficiente.  
  
> [!NOTE]
>  Oggetto `SafeCritical` restituzione del metodo `true` per entrambe <xref:System.Type.IsSecurityCritical%2A> e <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A>, in quanto `SafeCritical` è critical (ha le stesse funzionalità di codice critico, ma può essere chiamato da codice transparent).  
  
 I metodi dinamici ereditano la trasparenza dei moduli a cui sono allegati, mentre non ereditano la trasparenza del tipo, nel caso in cui siano allegati a un tipo.  
  
### <a name="skip-verification-in-full-trust"></a>Ignorare la verifica in attendibilità totale  
 È possibile ignorare la verifica degli assembly Transparent completamente attendibili impostando la proprietà <xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A> su `true` nell'attributo <xref:System.Security.SecurityRulesAttribute>:  
  
 `[assembly: SecurityRules(SecurityRuleSet.Level2, SkipVerificationInFullTrust = true)]`  
  
 La proprietà <xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A> è `false`e per impostazione predefinita, quindi deve essere impostata su `true` per ignorare la verifica. Questa operazione deve essere eseguita solo per ottimizzare le prestazioni. È necessario assicurarsi che il codice transparent dell'assembly sia verificabile con il `transparent` opzione il [strumento PEVerify](../../../docs/framework/tools/peverify-exe-peverify-tool.md).  
  
## <a name="see-also"></a>Vedere anche
- [Codice SecurityTransparent, livello 1](../../../docs/framework/misc/security-transparent-code-level-1.md)
- [Modifiche della sicurezza](../../../docs/framework/security/security-changes.md)
