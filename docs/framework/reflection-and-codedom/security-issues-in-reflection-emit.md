---
title: Problemi di sicurezza nella reflection emit
ms.date: 03/30/2017
helpviewer_keywords:
- partially trusted code
- emitting dynamic assemblies, security
- reflection emit, security
- reflection emit, partial trust scenarios
- partial trust,emitting dynamic methods
- anonymously hosted dynamic methods [.NET Framework]
- emitting dynamic assemblies,partial trust scenarios
- dynamic assemblies, security
ms.assetid: 0f8bf8fa-b993-478f-87ab-1a1a7976d298
ms.openlocfilehash: 11eb4c9bc4ba1b1fe9051a04d12f893e693fb175
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79180467"
---
# <a name="security-issues-in-reflection-emit"></a>Problemi di sicurezza nella reflection emit
.NET Framework offre tre modalità per creare codice Microsoft Intermediate Language (MSIL), ciascuna con specifici problemi di sicurezza:  
  
- [Assembly dinamici](#Dynamic_Assemblies)  
  
- [Metodi dinamici ospitati anonimamente](#Anonymously_Hosted_Dynamic_Methods)  
  
- [Metodi dinamici associati ad assembly esistenti](#Dynamic_Methods_Associated_with_Existing_Assemblies)  
  
 Indipendentemente dalla modalità di generazione del codice dinamico, l'esecuzione del codice generato richiede tutte le autorizzazioni necessarie per i tipi e i metodi usati dal codice generato.  
  
> [!NOTE]
> Le autorizzazioni necessarie per la reflection sul codice e sul codice di creazione sono state modificate nelle versioni successive di .NET Framework. Vedere [Informazioni sulla versione](#Version_Information) più avanti in questo argomento.  
  
<a name="Dynamic_Assemblies"></a>
## <a name="dynamic-assemblies"></a>Assembly dinamici  
 Gli assembly dinamici vengono creati usando gli overload del metodo <xref:System.AppDomain.DefineDynamicAssembly%2A?displayProperty=nameWithType>. La maggior parte degli overload di questo metodo sono deprecati in .NET Framework 4 a causa dell'eliminazione dei criteri di sicurezza a livello di computer. (Vedere [Modifiche alla sicurezza](../security/security-changes.md). Gli overload rimanenti possono essere eseguiti da qualsiasi codice, indipendentemente dal livello di attendibilità. Questi overload rientrano in due gruppi: quelli che specificano un elenco di attributi da applicare all'assembly dinamico quando viene creato e quelli che non lo specificano. Se non si specifica il modello di trasparenza per l'assembly, applicando l'attributo <xref:System.Security.SecurityRulesAttribute> durante la creazione, il modello di trasparenza viene ereditato dall'assembly di creazione.  
  
> [!NOTE]
> Gli attributi applicati all'assembly dinamico dopo averlo creato mediante il metodo <xref:System.Reflection.Emit.AssemblyBuilder.SetCustomAttribute%2A> non sono effettivi fino a quando l'assembly non viene salvato su disco e caricato di nuovo in memoria.  
  
 Il codice in un assembly dinamico può accedere a tipi e membri visibili in altri assembly.  
  
> [!NOTE]
> Gli assembly dinamici non usano i flag <xref:System.Security.Permissions.ReflectionPermissionFlag.MemberAccess?displayProperty=nameWithType> e <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType> che consentono ai metodi dinamici di accedere a tipi e membri non pubblici.  
  
 Gli assembly dinamici temporanei vengono creati in memoria e non vengono mai salvati su disco, pertanto non richiedono alcuna autorizzazione di accesso ai file. Il salvataggio di un assembly dinamico su disco richiede <xref:System.Security.Permissions.FileIOPermission> con flag appropriati.  
  
### <a name="generating-dynamic-assemblies-from-partially-trusted-code"></a>Generazione di assembly dinamici da codice parzialmente attendibile  
 Considerare le condizioni in cui un assembly con autorizzazioni Internet può generare un assembly dinamico temporaneo ed eseguirne il codice:  
  
- L'assembly dinamico usa solo tipi e membri pubblici di altri assembly.  
  
- Le autorizzazioni richieste da questi tipi e membri sono incluse nel set di concessioni dell'assembly parzialmente attendibile.  
  
- L'assembly non viene salvato su disco.  
  
- I simboli di debug non vengono generati. I set di autorizzazioni `Internet` e `LocalIntranet` non includono le autorizzazioni necessarie.  
  
<a name="Anonymously_Hosted_Dynamic_Methods"></a>
## <a name="anonymously-hosted-dynamic-methods"></a>Metodi dinamici ospitati anonimamente  
 I metodi dinamici ospitati anonimamente vengono creati usando i due costruttori <xref:System.Reflection.Emit.DynamicMethod> che non specificano un tipo o un modulo associato, <xref:System.Reflection.Emit.DynamicMethod.%23ctor%28System.String%2CSystem.Type%2CSystem.Type%5B%5D%29> e <xref:System.Reflection.Emit.DynamicMethod.%23ctor%28System.String%2CSystem.Type%2CSystem.Type%5B%5D%2CSystem.Boolean%29>. Questi costruttori inseriscono i metodi dinamici in un assembly fornito dal sistema, completamente attendibile, trasparente per la sicurezza. Non sono necessarie autorizzazioni per usare questi costruttori o per generare il codice per i metodi dinamici.  
  
 Al contrario, quando viene creato un metodo dinamico ospitato anonimamente, viene acquisito lo stack di chiamate. Quando il metodo viene costruito, le richieste di sicurezza vengono effettuate sullo stack di chiamate acquisito.  
  
> [!NOTE]
> Concettualmente, le richieste vengono effettuate durante la costruzione del metodo. In altre parole, le richieste potrebbero essere effettuate durante la creazione delle singole istruzioni MSIL. Nell'implementazione corrente tutte le richieste vengono effettuate quando il metodo <xref:System.Reflection.Emit.DynamicMethod.CreateDelegate%2A?displayProperty=nameWithType> viene chiamato o quando viene richiamato il compilatore Just-In-Time (JIT), se il metodo viene richiamato senza chiamare <xref:System.Reflection.Emit.DynamicMethod.CreateDelegate%2A>.  
  
 Se il dominio applicazione lo consente, i metodi dinamici ospitati anonimamente possono ignorare i controlli di visibilità JIT, ma solo se viene rispettata la restrizione seguente: i tipi e i membri non pubblici a cui accede un metodo dinamico ospitato anonimamente devono trovarsi in assembly i cui set di concessioni sono uguali o sono subset del set di concessioni dello stack di chiamate di creazione. Questa possibilità limitata di ignorare i controlli di visibilità JIT viene abilitata se il dominio applicazione concede <xref:System.Security.Permissions.ReflectionPermission> con il flag <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType>.  
  
- Se il metodo usa solo tipi e membri pubblici, non sono necessarie autorizzazioni durante la costruzione.  
  
- Se si specifica che i controlli di visibilità JIT debbano essere ignorati, la richiesta effettuata durante la costruzione del metodo includerà <xref:System.Security.Permissions.ReflectionPermission> con il flag <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType> e il set di concessioni dell'assembly che contiene il membro non pubblico a cui si accede.  
  
 Poiché il set di concessioni del membro non pubblico viene preso in considerazione, il codice parzialmente attendibile che ha ottenuto <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType> non può elevare i privilegi eseguendo membri non pubblici di assembly attendibili.  
  
 Come con qualsiasi altro codice generato, l'esecuzione del metodo dinamico richiede le autorizzazioni obbligatorie per i metodi usate dal metodo dinamico.  
  
 L'assembly di sistema che ospita i metodi dinamici ospitati in modo anonimo usa il modello di trasparenza <xref:System.Security.SecurityRuleSet.Level1?displayProperty=nameWithType>, usato in .NET Framework prima di .NET Framework 4.  
  
 Per altre informazioni, vedere la classe <xref:System.Reflection.Emit.DynamicMethod>.  
  
### <a name="generating-anonymously-hosted-dynamic-methods-from-partially-trusted-code"></a>Generazione di metodi dinamici ospitati anonimamente dal codice parzialmente attendibile  
 Considerare le condizioni in cui un assembly con autorizzazioni Internet può generare un metodo dinamico ospitato anonimamente ed eseguirlo:  
  
- Il metodo dinamico usa solo tipi e membri pubblici. Se il set di concessioni include <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType>, è possibile usare i tipi e i membri non pubblici di qualsiasi assembly il cui set di concessioni sia uguale o sia un subset del set di concessioni dell'assembly di creazione.  
  
- Le autorizzazioni necessarie per tutti i tipi e i membri usati dal metodo dinamico sono incluse nel set di concessioni dell'assembly parzialmente attendibile.  
  
> [!NOTE]
> I metodi dinamici non supportano i simboli di debug.  
  
<a name="Dynamic_Methods_Associated_with_Existing_Assemblies"></a>
## <a name="dynamic-methods-associated-with-existing-assemblies"></a>Metodi dinamici associati ad assembly esistenti  
 Per associare un metodo dinamico a un tipo o a un modulo in un assembly esistente, usare uno qualsiasi dei costruttori <xref:System.Reflection.Emit.DynamicMethod> che specificano il tipo o il modulo associato. Le autorizzazioni necessarie per chiamare questi costruttori variano, poiché l'associazione di un metodo dinamico a un tipo o a un modulo esistente fornisce al metodo dinamico l'accesso ai membri e ai tipi non pubblici:  
  
- Un metodo dinamico associato a un tipo può accedere a tutti i membri di tale tipo, anche ai membri privati, e a tutti i tipi e membri interni nell'assembly che contiene il tipo associato.  
  
- Un metodo dinamico associato a un modulo può accedere a tutti i tipi e membri di `internal` (`Friend` in Visual Basic, `assembly` nei metadati di Common Language Runtime) nel modulo.  
  
 Inoltre, è possibile usare un costruttore che consente di specificare la possibilità di ignorare i controlli di visibilità del compilatore JIT. In questo modo il metodo dinamico può accedere a tutti i tipi e membri in tutti gli assembly, indipendentemente dal livello di accesso.  
  
 Le autorizzazioni richieste dal costruttore dipendono dal livello di accesso che si decide di concedere al metodo dinamico:  
  
- Se il metodo usa solo membri e tipi pubblici e lo si associa a un tipo o a un modulo personalizzato, non sono necessarie autorizzazioni.  
  
- Se si specifica che devono essere ignorati i controlli di visibilità JIT, il costruttore richiede <xref:System.Security.Permissions.ReflectionPermission> con il flag <xref:System.Security.Permissions.ReflectionPermissionFlag.MemberAccess?displayProperty=nameWithType>.  
  
- Se si associa il metodo dinamico a un altro tipo, anche all'interno dell'assembly, il costruttore richiede <xref:System.Security.Permissions.ReflectionPermission> con il flag <xref:System.Security.Permissions.ReflectionPermissionFlag.MemberAccess?displayProperty=nameWithType> e <xref:System.Security.Permissions.SecurityPermission> con il flag <xref:System.Security.Permissions.SecurityPermissionFlag.ControlEvidence?displayProperty=nameWithType>.  
  
- Se si associa il metodo dinamico a un tipo o a un modulo in un altro assembly, il costruttore richiede due cose: <xref:System.Security.Permissions.ReflectionPermission> con il flag <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType> e il set di concessioni dell'assembly che contiene l'altro modulo. Ovvero, lo stack di chiamate deve includere tutte le autorizzazioni nel set di concessioni del modulo di destinazione, oltre a <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType>.  
  
    > [!NOTE]
    > Per la compatibilità con le versioni precedenti, se la richiesta per il set di concessioni di destinazione con <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType> ha esito negativo, il costruttore richiede <xref:System.Security.Permissions.SecurityPermission> con il flag <xref:System.Security.Permissions.SecurityPermissionFlag.ControlEvidence?displayProperty=nameWithType>.  
  
 Anche se gli elementi nell'elenco vengono descritti in termini di set di concessioni dell'assembly, tenere presente che le richieste vengono effettuate sullo stack di chiamate completo, incluso il limite del dominio applicazione.  
  
 Per altre informazioni, vedere la classe <xref:System.Reflection.Emit.DynamicMethod>.  
  
### <a name="generating-dynamic-methods-from-partially-trusted-code"></a>Generazione di metodi dinamici dal codice parzialmente attendibile  
  
> [!NOTE]
> Il metodo consigliato per generare metodi dinamici dal codice parzialmente attendibile consiste nell'usare [metodi dinamici ospitati anonimamente](#Anonymously_Hosted_Dynamic_Methods).  
  
 Considerare le condizioni in cui un assembly con autorizzazioni Internet può generare un metodo dinamico ed eseguirlo:  
  
- Il metodo dinamico è associato al modulo o al tipo che lo genera oppure il set di concessioni include <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType> ed è associato a un modulo in un assembly il cui set di concessioni è uguale o è un subset del set di concessioni dell'assembly di creazione.  
  
- Il metodo dinamico usa solo tipi e membri pubblici. Se il set di concessioni include <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType> ed è associato a un modulo in un assembly il cui set di concessioni è uguale o è un subset del set di concessioni dell'assembly di creazione, può usare tipi e membri contrassegnati come `internal` (`Friend` in Visual Basic, `assembly` nei metadati di Common Language Runtime) nel modulo associato.  
  
- Le autorizzazioni richieste da tutti i tipi e i membri usati dal metodo dinamico sono inclusi nel set di concessioni dell'assembly parzialmente attendibile.  
  
- Il metodo dinamico non ignora i controlli di visibilità JIT.  
  
> [!NOTE]
> I metodi dinamici non supportano i simboli di debug.  
  
<a name="Version_Information"></a>
## <a name="version-information"></a>Informazioni sulla versione  
 A partire da .NET Framework 4, i criteri di sicurezza a livello di computer vengono eliminati e la trasparenza della sicurezza diventa il meccanismo di imposizione predefinito. Vedere [Modifiche di sicurezza](../security/security-changes.md).  
  
 A partire da .NET Framework 2.0 Service Pack 1, non è più necessario usare <xref:System.Security.Permissions.ReflectionPermission> con il flag <xref:System.Security.Permissions.ReflectionPermissionFlag.ReflectionEmit?displayProperty=nameWithType> quando si generano assembly e metodi dinamici. Questo flag è richiesto in tutte le versioni precedenti di .NET Framework.  
  
> [!NOTE]
> <xref:System.Security.Permissions.ReflectionPermission> con il flag <xref:System.Security.Permissions.ReflectionPermissionFlag.ReflectionEmit?displayProperty=nameWithType> viene incluso per impostazione predefinita nei set di autorizzazioni denominati `FullTrust` e `LocalIntranet`, ma non nel set di autorizzazioni `Internet`. Pertanto, nelle versioni precedenti di .NET Framework è possibile usare una libreria con autorizzazioni Internet solo se viene eseguito un <xref:System.Security.PermissionSet.Assert%2A> per <xref:System.Security.Permissions.ReflectionPermissionFlag.ReflectionEmit>. Tali librerie richiedono un'attenta revisione della sicurezza perché eventuali errori nel codice potrebbe produrre delle vulnerabilità. .NET Framework 2.0 SP1 consente di generare codice in scenari con attendibilità parziale senza creare alcuna richiesta di sicurezza, poiché la generazione di codice non è implicitamente un'operazione con privilegi. Ovvero, il codice generato non dispone di ulteriori autorizzazioni rispetto all'assembly che lo genera. Questo consente alle librerie che generano il codice di essere SecurityTransparent ed elimina la necessità di asserire <xref:System.Security.Permissions.ReflectionPermissionFlag.ReflectionEmit>, che semplifica l'attività di scrittura di una libreria protetta.  
  
 .NET Framework 2.0 SP1 introduce inoltre il flag <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType> per l'accesso a tipi e membri non pubblici da metodi dinamici parzialmente attendibili. Le versioni precedenti di .NET Framework richiedono il flag <xref:System.Security.Permissions.ReflectionPermissionFlag.MemberAccess?displayProperty=nameWithType> per i metodi dinamici che accedono a membri e tipi non pubblici; si tratta di un'autorizzazione che non dovrebbe mai essere concessa a codice parzialmente attendibile.  
  
 .NET Framework 2.0 SP1 introduce infine i metodi ospitati anonimamente.  
  
### <a name="obtaining-information-on-types-and-members"></a>Informazioni su tipi e membri  
 A partire da .NET Framework 2.0 non sono necessarie autorizzazioni per ottenere informazioni sui tipi e i membri non pubblici. Per ottenere le informazioni necessarie a generare metodi dinamici viene usato Reflection. Ad esempio, gli oggetti <xref:System.Reflection.MethodInfo> vengono usati per generare le chiamate al metodo. Le versioni precedenti di .NET Framework richiedono <xref:System.Security.Permissions.ReflectionPermission> con il flag <xref:System.Security.Permissions.ReflectionPermissionFlag.TypeInformation?displayProperty=nameWithType>. Per altre informazioni, vedere [Security Considerations for Reflection](security-considerations-for-reflection.md) (Considerazioni sulla sicurezza per reflection).  
  
## <a name="see-also"></a>Vedere anche

- [Security Considerations for Reflection](security-considerations-for-reflection.md) (Considerazioni sulla sicurezza per reflection)
- [Creazione di assembly e metodi dinamici](emitting-dynamic-methods-and-assemblies.md)
