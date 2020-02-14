---
title: Codice trasparente per la sicurezza, livello 2
ms.date: 03/30/2017
helpviewer_keywords:
- transparency
- level 2 transparency
- security-transparent code
- security-critical code
ms.assetid: 4d05610a-0da6-4f08-acea-d54c9d6143c0
ms.openlocfilehash: 7ac5660c2c431505f4992f5e687974c2b9d06672
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217004"
---
# <a name="security-transparent-code-level-2"></a><span data-ttu-id="45e8a-102">Codice trasparente per la sicurezza, livello 2</span><span class="sxs-lookup"><span data-stu-id="45e8a-102">Security-Transparent Code, Level 2</span></span>

[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]

<span data-ttu-id="45e8a-103">La trasparenza di livello 2 è stata introdotta nel .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="45e8a-103">Level 2 transparency was introduced in the .NET Framework 4.</span></span> <span data-ttu-id="45e8a-104">I tre concetti principali di questo modello sono il codice Transparent, il codice SecuritySafeCritical e il codice SecurityCritical.</span><span class="sxs-lookup"><span data-stu-id="45e8a-104">The three tenets of this model are transparent code, security-safe-critical code, and security-critical code.</span></span>

- <span data-ttu-id="45e8a-105">Il codice Transparent, incluso il codice in esecuzione con attendibilità totale, può chiamare solo altro codice Transparent o codice SecuritySafeCritical.</span><span class="sxs-lookup"><span data-stu-id="45e8a-105">Transparent code, including code that is running as full trust, can call other transparent code or security-safe-critical code only.</span></span> <span data-ttu-id="45e8a-106">Può eseguire solo azioni consentite dal set di autorizzazioni parzialmente attendibile, se esistente, del dominio.</span><span class="sxs-lookup"><span data-stu-id="45e8a-106">It can only perform actions allowed by the domain’s partial trust permission set (if one exists).</span></span> <span data-ttu-id="45e8a-107">Il codice Transparent non può eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="45e8a-107">Transparent code cannot do the following:</span></span>

  - <span data-ttu-id="45e8a-108">Eseguire un metodo <xref:System.Security.CodeAccessPermission.Assert%2A> o un'elevazione dei privilegi.</span><span class="sxs-lookup"><span data-stu-id="45e8a-108">Perform an <xref:System.Security.CodeAccessPermission.Assert%2A> or elevation of privilege.</span></span>

  - <span data-ttu-id="45e8a-109">Contenere codice di tipo unsafe o non verificabile.</span><span class="sxs-lookup"><span data-stu-id="45e8a-109">Contain unsafe or unverifiable code.</span></span>

  - <span data-ttu-id="45e8a-110">Chiamare direttamente codice Critical.</span><span class="sxs-lookup"><span data-stu-id="45e8a-110">Directly call critical code.</span></span>

  - <span data-ttu-id="45e8a-111">Chiamare codice nativo o codice con l'attributo <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute>.</span><span class="sxs-lookup"><span data-stu-id="45e8a-111">Call native code or code with the <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> attribute.</span></span>

  - <span data-ttu-id="45e8a-112">Chiamare un membro protetto da <xref:System.Security.Permissions.SecurityAction.LinkDemand>.</span><span class="sxs-lookup"><span data-stu-id="45e8a-112">Call a member that is protected by a <xref:System.Security.Permissions.SecurityAction.LinkDemand>.</span></span>

  - <span data-ttu-id="45e8a-113">Ereditare dai tipi Critical.</span><span class="sxs-lookup"><span data-stu-id="45e8a-113">Inherit from critical types.</span></span>

  <span data-ttu-id="45e8a-114">Inoltre, i metodi Transparent non possono eseguire l'override di metodi virtuali Critical o implementare metodi di interfaccia Critical.</span><span class="sxs-lookup"><span data-stu-id="45e8a-114">In addition, transparent methods cannot override critical virtual methods or implement critical interface methods.</span></span>

- <span data-ttu-id="45e8a-115">Il codice SafeCritical è completamente attendibile, ma può essere chiamato dal codice Transparent.</span><span class="sxs-lookup"><span data-stu-id="45e8a-115">Safe-critical code is fully trusted but is callable by transparent code.</span></span> <span data-ttu-id="45e8a-116">Espone una superficie di attacco limitata di codice con attendibilità totale; nel codice SafeCritical vengono eseguite verifiche della correttezza e della sicurezza.</span><span class="sxs-lookup"><span data-stu-id="45e8a-116">It exposes a limited surface area of full-trust code; correctness and security verifications happen in safe-critical code.</span></span>

- <span data-ttu-id="45e8a-117">Il codice SecurityCritical può chiamare qualsiasi tipo di codice ed è completamente attendibile, ma non può essere chiamato da codice Transparent.</span><span class="sxs-lookup"><span data-stu-id="45e8a-117">Security-critical code can call any code and is fully trusted, but it cannot be called by transparent code.</span></span>

## <a name="usage-examples-and-behaviors"></a><span data-ttu-id="45e8a-118">Esempi di utilizzo e comportamenti</span><span class="sxs-lookup"><span data-stu-id="45e8a-118">Usage Examples and Behaviors</span></span>

<span data-ttu-id="45e8a-119">Per specificare .NET Framework 4 regole (trasparenza di livello 2), usare l'annotazione seguente per un assembly:</span><span class="sxs-lookup"><span data-stu-id="45e8a-119">To specify .NET Framework 4 rules (level 2 transparency), use the following annotation for an assembly:</span></span>

```csharp
[assembly: SecurityRules(SecurityRuleSet.Level2)]
```

<span data-ttu-id="45e8a-120">Per usare le regole di .NET Framework 2.0 (trasparenza di livello 1), usare l'annotazione seguente:</span><span class="sxs-lookup"><span data-stu-id="45e8a-120">To lock into the .NET Framework 2.0 rules (level 1 transparency), use the following annotation:</span></span>

```csharp
[assembly: SecurityRules(SecurityRuleSet.Level1)]
```

<span data-ttu-id="45e8a-121">Se non si annota un assembly, per impostazione predefinita vengono usate le regole .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="45e8a-121">If you do not annotate an assembly, the .NET Framework 4 rules are used by default.</span></span> <span data-ttu-id="45e8a-122">Tuttavia, la procedura consigliata consiste nell'usare l'attributo <xref:System.Security.SecurityRulesAttribute> anziché in base all'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="45e8a-122">However, the recommended best practice is to use the <xref:System.Security.SecurityRulesAttribute> attribute instead of depending on the default.</span></span>

### <a name="assembly-wide-annotation"></a><span data-ttu-id="45e8a-123">Annotazione a livello di assembly</span><span class="sxs-lookup"><span data-stu-id="45e8a-123">Assembly-wide Annotation</span></span>

<span data-ttu-id="45e8a-124">Le regole seguenti si applicano all'uso degli attributi a livello di assembly.</span><span class="sxs-lookup"><span data-stu-id="45e8a-124">The following rules apply to the use of attributes at the assembly level:</span></span>

- <span data-ttu-id="45e8a-125">Nessun attributo: se non si specificano attributi, il runtime interpreta tutto il codice come SecurityCritical, tranne nei casi in cui tale caratteristica viola una regola di ereditarietà, ad esempio quando si esegue l'override o l'implementazione di un metodo virtuale Transparent o di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="45e8a-125">No attributes: If you do not specify any attributes, the runtime interprets all code as security-critical, except where being security-critical violates an inheritance rule (for example, when overriding or implementing a transparent virtual or interface method).</span></span> <span data-ttu-id="45e8a-126">In tali casi, i metodi sono SafeCritical.</span><span class="sxs-lookup"><span data-stu-id="45e8a-126">In those cases, the methods are safe-critical.</span></span> <span data-ttu-id="45e8a-127">Se non si specificano attributi, Common Language Runtime determina automaticamente le regole di trasparenza.</span><span class="sxs-lookup"><span data-stu-id="45e8a-127">Specifying no attribute causes the common language runtime to determine the transparency rules for you.</span></span>

- <span data-ttu-id="45e8a-128">`SecurityTransparent`: tutto il codice è Transparent. L'intero assembly non eseguirà operazioni con privilegi o non sicure.</span><span class="sxs-lookup"><span data-stu-id="45e8a-128">`SecurityTransparent`: All code is transparent; the entire assembly will not do anything privileged or unsafe.</span></span>

- <span data-ttu-id="45e8a-129">`SecurityCritical`: tutto il codice introdotto dai tipi di questo assembly è Critical, mentre tutto l'altro codice è Transparent.</span><span class="sxs-lookup"><span data-stu-id="45e8a-129">`SecurityCritical`: All code that is introduced by types in this assembly is critical; all other code is transparent.</span></span> <span data-ttu-id="45e8a-130">Questo scenario è simile al caso in cui non vengono specificati attributi. Tuttavia Common Language Runtime non determina automaticamente le regole di trasparenza.</span><span class="sxs-lookup"><span data-stu-id="45e8a-130">This scenario is similar to not specifying any attributes; however, the common language runtime does not automatically determine the transparency rules.</span></span> <span data-ttu-id="45e8a-131">Se si esegue ad esempio l'override di un metodo virtuale o astratto oppure si implementa un metodo di interfaccia, per impostazione predefinita tale metodo è Transparent.</span><span class="sxs-lookup"><span data-stu-id="45e8a-131">For example, if you override a virtual or abstract method or implement an interface method, by default, that method is transparent.</span></span> <span data-ttu-id="45e8a-132">È necessario annotare in modo esplicito il metodo come `SecurityCritical` o `SecuritySafeCritical`; in caso contrario, verrà generata un'eccezione <xref:System.TypeLoadException> durante il caricamento.</span><span class="sxs-lookup"><span data-stu-id="45e8a-132">You must explicitly annotate the method as `SecurityCritical` or `SecuritySafeCritical`; otherwise, a <xref:System.TypeLoadException> will be thrown at load time.</span></span> <span data-ttu-id="45e8a-133">Questa regola si applica anche quando la classe base e la classe derivata si trovano nello stesso assembly.</span><span class="sxs-lookup"><span data-stu-id="45e8a-133">This rule also applies when both the base class and the derived class are in the same assembly.</span></span>

- <span data-ttu-id="45e8a-134">`AllowPartiallyTrustedCallers` (solo livello 2): tutto il codice è Transparent per impostazione predefinita. I singoli tipi e membri possono tuttavia avere altri attributi.</span><span class="sxs-lookup"><span data-stu-id="45e8a-134">`AllowPartiallyTrustedCallers` (level 2 only): All code defaults to transparent.</span></span> <span data-ttu-id="45e8a-135">I singoli tipi e membri possono tuttavia avere altri attributi.</span><span class="sxs-lookup"><span data-stu-id="45e8a-135">However, individual types and members can have other attributes.</span></span>

<span data-ttu-id="45e8a-136">Nella tabella seguente viene confrontato il comportamento a livello di assembly per il livello 2 con livello 1.</span><span class="sxs-lookup"><span data-stu-id="45e8a-136">The following table compares the assembly level behavior for Level 2 with Level 1.</span></span>

|<span data-ttu-id="45e8a-137">Attributo assembly</span><span class="sxs-lookup"><span data-stu-id="45e8a-137">Assembly attribute</span></span>|<span data-ttu-id="45e8a-138">Livello 2</span><span class="sxs-lookup"><span data-stu-id="45e8a-138">Level 2</span></span>|<span data-ttu-id="45e8a-139">Livello 1</span><span class="sxs-lookup"><span data-stu-id="45e8a-139">Level 1</span></span>|
|------------------------|-------------|-------------|
|<span data-ttu-id="45e8a-140">Nessun attributo su un assembly parzialmente attendibile</span><span class="sxs-lookup"><span data-stu-id="45e8a-140">No attribute on a partially trusted assembly</span></span>|<span data-ttu-id="45e8a-141">I tipi e i membri sono Transparent per impostazione predefinita, ma possono essere SecurityCritical o SecuritySafeCritical.</span><span class="sxs-lookup"><span data-stu-id="45e8a-141">Types and members are by default transparent, but can be security-critical or security-safe-critical.</span></span>|<span data-ttu-id="45e8a-142">Tutti i tipi e i membri sono Transparent.</span><span class="sxs-lookup"><span data-stu-id="45e8a-142">All types and members are transparent.</span></span>|
|<span data-ttu-id="45e8a-143">Nessun attributo</span><span class="sxs-lookup"><span data-stu-id="45e8a-143">No attribute</span></span>|<span data-ttu-id="45e8a-144">Se non si specificano attributi, Common Language Runtime determina automaticamente le regole di trasparenza.</span><span class="sxs-lookup"><span data-stu-id="45e8a-144">Specifying no attribute causes the common language runtime to determine the transparency rules for you.</span></span> <span data-ttu-id="45e8a-145">Tutti i tipi e i membri sono SecurityCritical, tranne nei casi in cui tale caratteristica viola una regola di ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="45e8a-145">All types and members are security-critical, except where being security-critical violates an inheritance rule.</span></span>|<span data-ttu-id="45e8a-146">In un assembly completamente attendibile (nella Global Assembly Cache o identificato come con attendibilità totale in `AppDomain`) tutti i tipi sono Transparent e tutti i membri sono SecuritySafeCritical.</span><span class="sxs-lookup"><span data-stu-id="45e8a-146">On a fully trusted assembly (in the global assembly cache or identified as full trust in the `AppDomain`) all types are transparent and all members are security-safe-critical.</span></span>|
|`SecurityTransparent`|<span data-ttu-id="45e8a-147">Tutti i tipi e i membri sono Transparent.</span><span class="sxs-lookup"><span data-stu-id="45e8a-147">All types and members are transparent.</span></span>|<span data-ttu-id="45e8a-148">Tutti i tipi e i membri sono Transparent.</span><span class="sxs-lookup"><span data-stu-id="45e8a-148">All types and members are transparent.</span></span>|
|`SecurityCritical(SecurityCriticalScope.Everything)`|<span data-ttu-id="45e8a-149">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="45e8a-149">Not applicable.</span></span>|<span data-ttu-id="45e8a-150">Tutti i tipi e i membri sono SecurityCritical.</span><span class="sxs-lookup"><span data-stu-id="45e8a-150">All types and members are security-critical.</span></span>|
|`SecurityCritical`|<span data-ttu-id="45e8a-151">Tutto il codice introdotto dai tipi di questo assembly è Critical, mentre tutto l'altro codice è Transparent.</span><span class="sxs-lookup"><span data-stu-id="45e8a-151">All code that is introduced by types in this assembly is critical; all other code is transparent.</span></span> <span data-ttu-id="45e8a-152">Se si esegue l'override di un metodo virtuale o astratto oppure si implementa un metodo di interfaccia, è necessario annotare in modo esplicito il metodo come `SecurityCritical` o `SecuritySafeCritical`.</span><span class="sxs-lookup"><span data-stu-id="45e8a-152">If you override a virtual or abstract method or implement an interface method, you must explicitly annotate the method as `SecurityCritical` or `SecuritySafeCritical`.</span></span>|<span data-ttu-id="45e8a-153">Tutto il codice è Transparent per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="45e8a-153">All code defaults to transparent.</span></span> <span data-ttu-id="45e8a-154">I singoli tipi e membri possono tuttavia avere altri attributi.</span><span class="sxs-lookup"><span data-stu-id="45e8a-154">However, individual types and members can have other attributes.</span></span>|

### <a name="type-and-member-annotation"></a><span data-ttu-id="45e8a-155">Annotazione dei tipi e dei membri</span><span class="sxs-lookup"><span data-stu-id="45e8a-155">Type and Member Annotation</span></span>

<span data-ttu-id="45e8a-156">Gli attributi di sicurezza applicati a un tipo si applicano anche ai membri introdotti dal tipo.</span><span class="sxs-lookup"><span data-stu-id="45e8a-156">The security attributes that are applied to a type also apply to the members that are introduced by the type.</span></span> <span data-ttu-id="45e8a-157">Non si applicano tuttavia a override virtuali o astratti della classe base o delle implementazioni dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="45e8a-157">However, they do not apply to virtual or abstract overrides of the base class or interface implementations.</span></span> <span data-ttu-id="45e8a-158">Le regole seguenti si applicano all'uso degli attributi a livello di tipo e membro:</span><span class="sxs-lookup"><span data-stu-id="45e8a-158">The following rules apply to the use of attributes at the type and member level:</span></span>

- <span data-ttu-id="45e8a-159">`SecurityCritical`: il tipo o il membro è Critical e può essere chiamato solo da codice con attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="45e8a-159">`SecurityCritical`: The type or member is critical and can be called only by full-trust code.</span></span> <span data-ttu-id="45e8a-160">I metodi introdotti in un tipo SecurityCritical sono Critical.</span><span class="sxs-lookup"><span data-stu-id="45e8a-160">Methods that are introduced in a security-critical type are critical.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="45e8a-161">I metodi virtuali e astratti introdotti in classi base o interfacce e sottoposti a override o implementati in una classe SecurityCritical sono Transparent per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="45e8a-161">Virtual and abstract methods that are introduced in base classes or interfaces, and overridden or implemented in a security-critical class are transparent by default.</span></span> <span data-ttu-id="45e8a-162">Devono essere identificati come `SecuritySafeCritical` o `SecurityCritical`.</span><span class="sxs-lookup"><span data-stu-id="45e8a-162">They must be identified as either `SecuritySafeCritical` or `SecurityCritical`.</span></span>

- <span data-ttu-id="45e8a-163">`SecuritySafeCritical`: il tipo o il membro è SafeCritical.</span><span class="sxs-lookup"><span data-stu-id="45e8a-163">`SecuritySafeCritical`: The type or member is safe-critical.</span></span> <span data-ttu-id="45e8a-164">Il tipo o il membro può tuttavia essere chiamato da codice Transparent (parzialmente attendibile) e funziona come qualsiasi altro codice Critical.</span><span class="sxs-lookup"><span data-stu-id="45e8a-164">However, the type or member can be called from transparent (partially trusted) code and is as capable as any other critical code.</span></span> <span data-ttu-id="45e8a-165">Il codice deve essere controllato per garantirne la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="45e8a-165">The code must be audited for security.</span></span>

## <a name="override-patterns"></a><span data-ttu-id="45e8a-166">Criteri di override</span><span class="sxs-lookup"><span data-stu-id="45e8a-166">Override Patterns</span></span>

<span data-ttu-id="45e8a-167">Nella tabella seguente vengono elencati gli override dei metodi consentiti per la trasparenza di livello 2.</span><span class="sxs-lookup"><span data-stu-id="45e8a-167">The following table shows the method overrides allowed for level 2 transparency.</span></span>

|<span data-ttu-id="45e8a-168">Membro di base virtuale/di interfaccia</span><span class="sxs-lookup"><span data-stu-id="45e8a-168">Base virtual/interface member</span></span>|<span data-ttu-id="45e8a-169">Override/interfaccia</span><span class="sxs-lookup"><span data-stu-id="45e8a-169">Override/interface</span></span>|
|------------------------------------|-------------------------|
|`Transparent`|`Transparent`|
|`Transparent`|`SafeCritical`|
|`SafeCritical`|`Transparent`|
|`SafeCritical`|`SafeCritical`|
|`Critical`|`Critical`|

## <a name="inheritance-rules"></a><span data-ttu-id="45e8a-170">Regole di ereditarietà</span><span class="sxs-lookup"><span data-stu-id="45e8a-170">Inheritance Rules</span></span>

<span data-ttu-id="45e8a-171">In questa sezione, l'ordine seguente è assegnato al codice `Transparent`, `Critical` e `SafeCritical` in base all'accesso e alle funzionalità:</span><span class="sxs-lookup"><span data-stu-id="45e8a-171">In this section, the following order is assigned to `Transparent`, `Critical`, and `SafeCritical` code based on access and capabilities:</span></span>

`Transparent` < `SafeCritical` < `Critical`

- <span data-ttu-id="45e8a-172">Regole per i tipi: da sinistra verso destra l'accesso diventa più restrittivo.</span><span class="sxs-lookup"><span data-stu-id="45e8a-172">Rules for types: Going from left to right, access becomes more restrictive.</span></span> <span data-ttu-id="45e8a-173">I tipi derivati devono essere restrittivi almeno quanto il tipo di base.</span><span class="sxs-lookup"><span data-stu-id="45e8a-173">Derived types must be at least as restrictive as the base type.</span></span>

- <span data-ttu-id="45e8a-174">Regole per i metodi: i metodi derivati non possono modificare l'accessibilità dal metodo di base.</span><span class="sxs-lookup"><span data-stu-id="45e8a-174">Rules for methods: Derived methods cannot change accessibility from the base method.</span></span> <span data-ttu-id="45e8a-175">Per il comportamento predefinito, tutti i metodi derivati non annotati sono `Transparent`.</span><span class="sxs-lookup"><span data-stu-id="45e8a-175">For default behavior, all derived methods that are not annotated are `Transparent`.</span></span> <span data-ttu-id="45e8a-176">I derivati di tipi Critical provocano un'eccezione se il metodo sottoposto a override non è annotato in modo esplicito come `SecurityCritical`.</span><span class="sxs-lookup"><span data-stu-id="45e8a-176">Derivatives of critical types cause an exception to be thrown if the overridden method is not explicitly annotated as `SecurityCritical`.</span></span>

<span data-ttu-id="45e8a-177">Nella tabella seguente vengono elencati i criteri dell'ereditarietà dei tipi consentiti.</span><span class="sxs-lookup"><span data-stu-id="45e8a-177">The following table shows the allowed type inheritance patterns.</span></span>

|<span data-ttu-id="45e8a-178">Classe di base</span><span class="sxs-lookup"><span data-stu-id="45e8a-178">Base class</span></span>|<span data-ttu-id="45e8a-179">La classe derivata può essere</span><span class="sxs-lookup"><span data-stu-id="45e8a-179">Derived class can be</span></span>|
|----------------|--------------------------|
|`Transparent`|`Transparent`|
|`Transparent`|`SafeCritical`|
|`Transparent`|`Critical`|
|`SafeCritical`|`SafeCritical`|
|`SafeCritical`|`Critical`|
|`Critical`|`Critical`|

<span data-ttu-id="45e8a-180">Nella tabella seguente vengono elencati i criteri di ereditarietà dei tipi non consentiti.</span><span class="sxs-lookup"><span data-stu-id="45e8a-180">The following table shows the disallowed type inheritance patterns.</span></span>

|<span data-ttu-id="45e8a-181">Classe di base</span><span class="sxs-lookup"><span data-stu-id="45e8a-181">Base class</span></span>|<span data-ttu-id="45e8a-182">La classe derivata non può essere</span><span class="sxs-lookup"><span data-stu-id="45e8a-182">Derived class cannot be</span></span>|
|----------------|-----------------------------|
|`SafeCritical`|`Transparent`|
|`Critical`|`Transparent`|
|`Critical`|`SafeCritical`|

<span data-ttu-id="45e8a-183">Nella tabella seguente vengono elencati i criteri di ereditarietà dei metodi consentiti.</span><span class="sxs-lookup"><span data-stu-id="45e8a-183">The following table shows the allowed method inheritance patterns.</span></span>

|<span data-ttu-id="45e8a-184">Metodo di base</span><span class="sxs-lookup"><span data-stu-id="45e8a-184">Base method</span></span>|<span data-ttu-id="45e8a-185">Il metodo derivato può essere</span><span class="sxs-lookup"><span data-stu-id="45e8a-185">Derived method can be</span></span>|
|-----------------|---------------------------|
|`Transparent`|`Transparent`|
|`Transparent`|`SafeCritical`|
|`SafeCritical`|`Transparent`|
|`SafeCritical`|`SafeCritical`|
|`Critical`|`Critical`|

<span data-ttu-id="45e8a-186">Nella tabella seguente vengono elencati i criteri di ereditarietà dei metodi non consentiti.</span><span class="sxs-lookup"><span data-stu-id="45e8a-186">The following table shows the disallowed method inheritance patterns.</span></span>

|<span data-ttu-id="45e8a-187">Metodo di base</span><span class="sxs-lookup"><span data-stu-id="45e8a-187">Base method</span></span>|<span data-ttu-id="45e8a-188">Il metodo derivato non può essere</span><span class="sxs-lookup"><span data-stu-id="45e8a-188">Derived method cannot be</span></span>|
|-----------------|------------------------------|
|`Transparent`|`Critical`|
|`SafeCritical`|`Critical`|
|`Critical`|`Transparent`|
|`Critical`|`SafeCritical`|

> [!NOTE]
> <span data-ttu-id="45e8a-189">Queste regole di ereditarietà si applicano a tipi e membri di livello 2.</span><span class="sxs-lookup"><span data-stu-id="45e8a-189">These inheritance rules apply to level 2 types and members.</span></span> <span data-ttu-id="45e8a-190">I tipi di assembly di livello 1 possono ereditare dai membri e dai tipi SecurityCritical di livello 2.</span><span class="sxs-lookup"><span data-stu-id="45e8a-190">Types in level 1 assemblies can inherit from level 2 security-critical types and members.</span></span> <span data-ttu-id="45e8a-191">Pertanto, i tipi e i membri di livello 2 devono disporre di richieste di ereditarietà separate per gli eredi di livello 1.</span><span class="sxs-lookup"><span data-stu-id="45e8a-191">Therefore, level 2 types and members must have separate inheritance demands for level 1 inheritors.</span></span>

## <a name="additional-information-and-rules"></a><span data-ttu-id="45e8a-192">Informazioni e regole aggiuntive</span><span class="sxs-lookup"><span data-stu-id="45e8a-192">Additional Information and Rules</span></span>

### <a name="linkdemand-support"></a><span data-ttu-id="45e8a-193">Supporto LinkDemand</span><span class="sxs-lookup"><span data-stu-id="45e8a-193">LinkDemand Support</span></span>

<span data-ttu-id="45e8a-194">Nel modello di trasparenza di livello 2, <xref:System.Security.Permissions.SecurityAction.LinkDemand> è stato sostituito dall'attributo <xref:System.Security.SecurityCriticalAttribute>.</span><span class="sxs-lookup"><span data-stu-id="45e8a-194">The level 2 transparency model replaces the <xref:System.Security.Permissions.SecurityAction.LinkDemand> with the <xref:System.Security.SecurityCriticalAttribute> attribute.</span></span> <span data-ttu-id="45e8a-195">Nel codice legacy (livello 1), <xref:System.Security.Permissions.SecurityAction.LinkDemand> viene trattato automaticamente come <xref:System.Security.Permissions.SecurityAction.Demand>.</span><span class="sxs-lookup"><span data-stu-id="45e8a-195">In legacy (level 1) code, a <xref:System.Security.Permissions.SecurityAction.LinkDemand> is automatically treated as a <xref:System.Security.Permissions.SecurityAction.Demand>.</span></span>

### <a name="reflection"></a><span data-ttu-id="45e8a-196">Reflection</span><span class="sxs-lookup"><span data-stu-id="45e8a-196">Reflection</span></span>

<span data-ttu-id="45e8a-197">Se si richiama un metodo Critical o si legge un campo Critical, viene generata una richiesta di attendibilità totale, come se si stesse richiamando un metodo o un campo Private.</span><span class="sxs-lookup"><span data-stu-id="45e8a-197">Invoking a critical method or reading a critical field triggers a demand for full trust (just as if you were invoking a private method or field).</span></span> <span data-ttu-id="45e8a-198">Il codice con attendibilità totale può quindi richiamare un metodo Critical, a differenza del codice parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="45e8a-198">Therefore, full-trust code can invoke a critical method, whereas partial-trust code cannot.</span></span>

<span data-ttu-id="45e8a-199">Le proprietà seguenti sono state aggiunte allo spazio dei nomi di <xref:System.Reflection> per determinare se il tipo, il metodo, o il campo è `SecurityCritical`, `SecuritySafeCritical` o `SecurityTransparent`: <xref:System.Type.IsSecurityCritical%2A>, <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A> e <xref:System.Reflection.MethodBase.IsSecurityTransparent%2A>.</span><span class="sxs-lookup"><span data-stu-id="45e8a-199">The following properties have been added to the <xref:System.Reflection> namespace to determine whether the type, method, or field is `SecurityCritical`, `SecuritySafeCritical`, or `SecurityTransparent`:  <xref:System.Type.IsSecurityCritical%2A>, <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A>, and <xref:System.Reflection.MethodBase.IsSecurityTransparent%2A>.</span></span> <span data-ttu-id="45e8a-200">Usare queste proprietà per determinare la trasparenza con reflection anziché verificare la presenza dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="45e8a-200">Use these properties to determine transparency by using reflection instead of checking for the presence of the attribute.</span></span> <span data-ttu-id="45e8a-201">Le regole di trasparenza sono complesse ed la verifica dell'attributo potrebbe non essere sufficiente.</span><span class="sxs-lookup"><span data-stu-id="45e8a-201">The transparency rules are complex, and checking for the attribute may not be sufficient.</span></span>

> [!NOTE]
> <span data-ttu-id="45e8a-202">Un metodo di `SafeCritical` restituisce `true` sia per <xref:System.Type.IsSecurityCritical%2A> che per <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A>, perché `SafeCritical` è effettivamente critico (presenta le stesse funzionalità del codice critico, ma può essere chiamato dal codice trasparente).</span><span class="sxs-lookup"><span data-stu-id="45e8a-202">A `SafeCritical` method returns `true` for both <xref:System.Type.IsSecurityCritical%2A> and <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A>, because `SafeCritical` is indeed critical (it has the same capabilities as critical code, but it can be called from transparent code).</span></span>

<span data-ttu-id="45e8a-203">I metodi dinamici ereditano la trasparenza dei moduli a cui sono allegati, mentre non ereditano la trasparenza del tipo, nel caso in cui siano allegati a un tipo.</span><span class="sxs-lookup"><span data-stu-id="45e8a-203">Dynamic methods inherit the transparency of the modules they are attached to; they do not inherit the transparency of the type (if they are attached to a type).</span></span>

### <a name="skip-verification-in-full-trust"></a><span data-ttu-id="45e8a-204">Ignorare la verifica in attendibilità totale</span><span class="sxs-lookup"><span data-stu-id="45e8a-204">Skip Verification in Full Trust</span></span>

<span data-ttu-id="45e8a-205">È possibile ignorare la verifica degli assembly Transparent completamente attendibili impostando la proprietà <xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A> su `true` nell'attributo <xref:System.Security.SecurityRulesAttribute>:</span><span class="sxs-lookup"><span data-stu-id="45e8a-205">You can skip verification for fully trusted transparent assemblies by setting the <xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A> property to `true` in the <xref:System.Security.SecurityRulesAttribute> attribute:</span></span>

`[assembly: SecurityRules(SecurityRuleSet.Level2, SkipVerificationInFullTrust = true)]`

<span data-ttu-id="45e8a-206">La proprietà <xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A> è `false`e per impostazione predefinita, quindi deve essere impostata su `true` per ignorare la verifica.</span><span class="sxs-lookup"><span data-stu-id="45e8a-206">The <xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A> property is `false` by default, so the property must be set to `true` to skip verification.</span></span> <span data-ttu-id="45e8a-207">Questa operazione deve essere eseguita solo per ottimizzare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="45e8a-207">This should be done for optimization purposes only.</span></span> <span data-ttu-id="45e8a-208">È necessario assicurarsi che il codice Transparent nell'assembly sia verificabile tramite l'opzione `transparent` nello [strumento PEVerify](../tools/peverify-exe-peverify-tool.md).</span><span class="sxs-lookup"><span data-stu-id="45e8a-208">You should ensure that the transparent code in the assembly is verifiable by using the `transparent` option in the [PEVerify tool](../tools/peverify-exe-peverify-tool.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="45e8a-209">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="45e8a-209">See also</span></span>

- [<span data-ttu-id="45e8a-210">Codice SecurityTransparent, livello 1</span><span class="sxs-lookup"><span data-stu-id="45e8a-210">Security-Transparent Code, Level 1</span></span>](security-transparent-code-level-1.md)
- [<span data-ttu-id="45e8a-211">Modifiche della sicurezza</span><span class="sxs-lookup"><span data-stu-id="45e8a-211">Security Changes</span></span>](../security/security-changes.md)
