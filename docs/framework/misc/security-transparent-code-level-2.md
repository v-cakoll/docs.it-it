---
title: Codice SecurityTransparent, livello 2
description: Comprendere il codice Transparent di livello 2. Vedere esempi e comportamenti di utilizzo, modelli di override, regole di ereditarietà e altro ancora.
ms.date: 03/30/2017
helpviewer_keywords:
- transparency
- level 2 transparency
- security-transparent code
- security-critical code
ms.assetid: 4d05610a-0da6-4f08-acea-d54c9d6143c0
ms.openlocfilehash: 3b87a48ac3f9925fd868be9e58d5904014ca6c09
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309209"
---
# <a name="security-transparent-code-level-2"></a><span data-ttu-id="e4de9-104">Codice SecurityTransparent, livello 2</span><span class="sxs-lookup"><span data-stu-id="e4de9-104">Security-Transparent Code, Level 2</span></span>

[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]

<span data-ttu-id="e4de9-105">La trasparenza di livello 2 è stata introdotta nel .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="e4de9-105">Level 2 transparency was introduced in the .NET Framework 4.</span></span> <span data-ttu-id="e4de9-106">I tre concetti principali di questo modello sono il codice Transparent, il codice SecuritySafeCritical e il codice SecurityCritical.</span><span class="sxs-lookup"><span data-stu-id="e4de9-106">The three tenets of this model are transparent code, security-safe-critical code, and security-critical code.</span></span>

- <span data-ttu-id="e4de9-107">Il codice Transparent, incluso il codice in esecuzione con attendibilità totale, può chiamare solo altro codice Transparent o codice SecuritySafeCritical.</span><span class="sxs-lookup"><span data-stu-id="e4de9-107">Transparent code, including code that is running as full trust, can call other transparent code or security-safe-critical code only.</span></span> <span data-ttu-id="e4de9-108">Può eseguire solo azioni consentite dal set di autorizzazioni parzialmente attendibile, se esistente, del dominio.</span><span class="sxs-lookup"><span data-stu-id="e4de9-108">It can only perform actions allowed by the domain’s partial trust permission set (if one exists).</span></span> <span data-ttu-id="e4de9-109">Il codice Transparent non può eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e4de9-109">Transparent code cannot do the following:</span></span>

  - <span data-ttu-id="e4de9-110">Eseguire un metodo <xref:System.Security.CodeAccessPermission.Assert%2A> o un'elevazione dei privilegi.</span><span class="sxs-lookup"><span data-stu-id="e4de9-110">Perform an <xref:System.Security.CodeAccessPermission.Assert%2A> or elevation of privilege.</span></span>

  - <span data-ttu-id="e4de9-111">Contenere codice di tipo unsafe o non verificabile.</span><span class="sxs-lookup"><span data-stu-id="e4de9-111">Contain unsafe or unverifiable code.</span></span>

  - <span data-ttu-id="e4de9-112">Chiamare direttamente codice Critical.</span><span class="sxs-lookup"><span data-stu-id="e4de9-112">Directly call critical code.</span></span>

  - <span data-ttu-id="e4de9-113">Chiamare codice nativo o codice con l'attributo <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute>.</span><span class="sxs-lookup"><span data-stu-id="e4de9-113">Call native code or code with the <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> attribute.</span></span>

  - <span data-ttu-id="e4de9-114">Chiamare un membro protetto da <xref:System.Security.Permissions.SecurityAction.LinkDemand>.</span><span class="sxs-lookup"><span data-stu-id="e4de9-114">Call a member that is protected by a <xref:System.Security.Permissions.SecurityAction.LinkDemand>.</span></span>

  - <span data-ttu-id="e4de9-115">Ereditare dai tipi Critical.</span><span class="sxs-lookup"><span data-stu-id="e4de9-115">Inherit from critical types.</span></span>

  <span data-ttu-id="e4de9-116">Inoltre, i metodi Transparent non possono eseguire l'override di metodi virtuali Critical o implementare metodi di interfaccia Critical.</span><span class="sxs-lookup"><span data-stu-id="e4de9-116">In addition, transparent methods cannot override critical virtual methods or implement critical interface methods.</span></span>

- <span data-ttu-id="e4de9-117">Il codice SafeCritical è completamente attendibile, ma può essere chiamato dal codice Transparent.</span><span class="sxs-lookup"><span data-stu-id="e4de9-117">Safe-critical code is fully trusted but is callable by transparent code.</span></span> <span data-ttu-id="e4de9-118">Espone una superficie di attacco limitata di codice con attendibilità totale; nel codice SafeCritical vengono eseguite verifiche della correttezza e della sicurezza.</span><span class="sxs-lookup"><span data-stu-id="e4de9-118">It exposes a limited surface area of full-trust code; correctness and security verifications happen in safe-critical code.</span></span>

- <span data-ttu-id="e4de9-119">Il codice SecurityCritical può chiamare qualsiasi tipo di codice ed è completamente attendibile, ma non può essere chiamato da codice Transparent.</span><span class="sxs-lookup"><span data-stu-id="e4de9-119">Security-critical code can call any code and is fully trusted, but it cannot be called by transparent code.</span></span>

## <a name="usage-examples-and-behaviors"></a><span data-ttu-id="e4de9-120">Esempi di utilizzo e comportamenti</span><span class="sxs-lookup"><span data-stu-id="e4de9-120">Usage Examples and Behaviors</span></span>

<span data-ttu-id="e4de9-121">Per specificare .NET Framework 4 regole (trasparenza di livello 2), usare l'annotazione seguente per un assembly:</span><span class="sxs-lookup"><span data-stu-id="e4de9-121">To specify .NET Framework 4 rules (level 2 transparency), use the following annotation for an assembly:</span></span>

```csharp
[assembly: SecurityRules(SecurityRuleSet.Level2)]
```

<span data-ttu-id="e4de9-122">Per usare le regole di .NET Framework 2.0 (trasparenza di livello 1), usare l'annotazione seguente:</span><span class="sxs-lookup"><span data-stu-id="e4de9-122">To lock into the .NET Framework 2.0 rules (level 1 transparency), use the following annotation:</span></span>

```csharp
[assembly: SecurityRules(SecurityRuleSet.Level1)]
```

<span data-ttu-id="e4de9-123">Se non si annota un assembly, per impostazione predefinita vengono usate le regole .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="e4de9-123">If you do not annotate an assembly, the .NET Framework 4 rules are used by default.</span></span> <span data-ttu-id="e4de9-124">Tuttavia, la procedura consigliata consiste nell'usare l' <xref:System.Security.SecurityRulesAttribute> attributo anziché in base all'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="e4de9-124">However, the recommended best practice is to use the <xref:System.Security.SecurityRulesAttribute> attribute instead of depending on the default.</span></span>

### <a name="assembly-wide-annotation"></a><span data-ttu-id="e4de9-125">Annotazione a livello di assembly</span><span class="sxs-lookup"><span data-stu-id="e4de9-125">Assembly-wide Annotation</span></span>

<span data-ttu-id="e4de9-126">Le regole seguenti si applicano all'uso degli attributi a livello di assembly.</span><span class="sxs-lookup"><span data-stu-id="e4de9-126">The following rules apply to the use of attributes at the assembly level:</span></span>

- <span data-ttu-id="e4de9-127">Nessun attributo: se non si specificano attributi, il runtime interpreta tutto il codice come SecurityCritical, tranne nei casi in cui tale caratteristica viola una regola di ereditarietà, ad esempio quando si esegue l'override o l'implementazione di un metodo virtuale Transparent o di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="e4de9-127">No attributes: If you do not specify any attributes, the runtime interprets all code as security-critical, except where being security-critical violates an inheritance rule (for example, when overriding or implementing a transparent virtual or interface method).</span></span> <span data-ttu-id="e4de9-128">In tali casi, i metodi sono SafeCritical.</span><span class="sxs-lookup"><span data-stu-id="e4de9-128">In those cases, the methods are safe-critical.</span></span> <span data-ttu-id="e4de9-129">Se non si specificano attributi, Common Language Runtime determina automaticamente le regole di trasparenza.</span><span class="sxs-lookup"><span data-stu-id="e4de9-129">Specifying no attribute causes the common language runtime to determine the transparency rules for you.</span></span>

- <span data-ttu-id="e4de9-130">`SecurityTransparent`: tutto il codice è Transparent. L'intero assembly non eseguirà operazioni con privilegi o non sicure.</span><span class="sxs-lookup"><span data-stu-id="e4de9-130">`SecurityTransparent`: All code is transparent; the entire assembly will not do anything privileged or unsafe.</span></span>

- <span data-ttu-id="e4de9-131">`SecurityCritical`: tutto il codice introdotto dai tipi di questo assembly è Critical, mentre tutto l'altro codice è Transparent.</span><span class="sxs-lookup"><span data-stu-id="e4de9-131">`SecurityCritical`: All code that is introduced by types in this assembly is critical; all other code is transparent.</span></span> <span data-ttu-id="e4de9-132">Questo scenario è simile al caso in cui non vengono specificati attributi. Tuttavia Common Language Runtime non determina automaticamente le regole di trasparenza.</span><span class="sxs-lookup"><span data-stu-id="e4de9-132">This scenario is similar to not specifying any attributes; however, the common language runtime does not automatically determine the transparency rules.</span></span> <span data-ttu-id="e4de9-133">Se si esegue ad esempio l'override di un metodo virtuale o astratto oppure si implementa un metodo di interfaccia, per impostazione predefinita tale metodo è Transparent.</span><span class="sxs-lookup"><span data-stu-id="e4de9-133">For example, if you override a virtual or abstract method or implement an interface method, by default, that method is transparent.</span></span> <span data-ttu-id="e4de9-134">È necessario annotare in modo esplicito il metodo come `SecurityCritical` o `SecuritySafeCritical`; in caso contrario, verrà generata un'eccezione <xref:System.TypeLoadException> durante il caricamento.</span><span class="sxs-lookup"><span data-stu-id="e4de9-134">You must explicitly annotate the method as `SecurityCritical` or `SecuritySafeCritical`; otherwise, a <xref:System.TypeLoadException> will be thrown at load time.</span></span> <span data-ttu-id="e4de9-135">Questa regola si applica anche quando la classe base e la classe derivata si trovano nello stesso assembly.</span><span class="sxs-lookup"><span data-stu-id="e4de9-135">This rule also applies when both the base class and the derived class are in the same assembly.</span></span>

- <span data-ttu-id="e4de9-136">`AllowPartiallyTrustedCallers` (solo livello 2): tutto il codice è Transparent per impostazione predefinita. I singoli tipi e membri possono tuttavia avere altri attributi.</span><span class="sxs-lookup"><span data-stu-id="e4de9-136">`AllowPartiallyTrustedCallers` (level 2 only): All code defaults to transparent.</span></span> <span data-ttu-id="e4de9-137">I singoli tipi e membri possono tuttavia avere altri attributi.</span><span class="sxs-lookup"><span data-stu-id="e4de9-137">However, individual types and members can have other attributes.</span></span>

<span data-ttu-id="e4de9-138">Nella tabella seguente viene confrontato il comportamento a livello di assembly per il livello 2 con livello 1.</span><span class="sxs-lookup"><span data-stu-id="e4de9-138">The following table compares the assembly level behavior for Level 2 with Level 1.</span></span>

|<span data-ttu-id="e4de9-139">Attributo assembly</span><span class="sxs-lookup"><span data-stu-id="e4de9-139">Assembly attribute</span></span>|<span data-ttu-id="e4de9-140">Livello 2</span><span class="sxs-lookup"><span data-stu-id="e4de9-140">Level 2</span></span>|<span data-ttu-id="e4de9-141">Livello 1</span><span class="sxs-lookup"><span data-stu-id="e4de9-141">Level 1</span></span>|
|------------------------|-------------|-------------|
|<span data-ttu-id="e4de9-142">Nessun attributo su un assembly parzialmente attendibile</span><span class="sxs-lookup"><span data-stu-id="e4de9-142">No attribute on a partially trusted assembly</span></span>|<span data-ttu-id="e4de9-143">I tipi e i membri sono Transparent per impostazione predefinita, ma possono essere SecurityCritical o SecuritySafeCritical.</span><span class="sxs-lookup"><span data-stu-id="e4de9-143">Types and members are by default transparent, but can be security-critical or security-safe-critical.</span></span>|<span data-ttu-id="e4de9-144">Tutti i tipi e i membri sono Transparent.</span><span class="sxs-lookup"><span data-stu-id="e4de9-144">All types and members are transparent.</span></span>|
|<span data-ttu-id="e4de9-145">Nessun attributo</span><span class="sxs-lookup"><span data-stu-id="e4de9-145">No attribute</span></span>|<span data-ttu-id="e4de9-146">Se non si specificano attributi, Common Language Runtime determina automaticamente le regole di trasparenza.</span><span class="sxs-lookup"><span data-stu-id="e4de9-146">Specifying no attribute causes the common language runtime to determine the transparency rules for you.</span></span> <span data-ttu-id="e4de9-147">Tutti i tipi e i membri sono SecurityCritical, tranne nei casi in cui tale caratteristica viola una regola di ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="e4de9-147">All types and members are security-critical, except where being security-critical violates an inheritance rule.</span></span>|<span data-ttu-id="e4de9-148">In un assembly completamente attendibile (nella Global Assembly Cache o identificato come con attendibilità totale in `AppDomain`) tutti i tipi sono Transparent e tutti i membri sono SecuritySafeCritical.</span><span class="sxs-lookup"><span data-stu-id="e4de9-148">On a fully trusted assembly (in the global assembly cache or identified as full trust in the `AppDomain`) all types are transparent and all members are security-safe-critical.</span></span>|
|`SecurityTransparent`|<span data-ttu-id="e4de9-149">Tutti i tipi e i membri sono Transparent.</span><span class="sxs-lookup"><span data-stu-id="e4de9-149">All types and members are transparent.</span></span>|<span data-ttu-id="e4de9-150">Tutti i tipi e i membri sono Transparent.</span><span class="sxs-lookup"><span data-stu-id="e4de9-150">All types and members are transparent.</span></span>|
|`SecurityCritical(SecurityCriticalScope.Everything)`|<span data-ttu-id="e4de9-151">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="e4de9-151">Not applicable.</span></span>|<span data-ttu-id="e4de9-152">Tutti i tipi e i membri sono SecurityCritical.</span><span class="sxs-lookup"><span data-stu-id="e4de9-152">All types and members are security-critical.</span></span>|
|`SecurityCritical`|<span data-ttu-id="e4de9-153">Tutto il codice introdotto dai tipi di questo assembly è Critical, mentre tutto l'altro codice è Transparent.</span><span class="sxs-lookup"><span data-stu-id="e4de9-153">All code that is introduced by types in this assembly is critical; all other code is transparent.</span></span> <span data-ttu-id="e4de9-154">Se si esegue l'override di un metodo virtuale o astratto oppure si implementa un metodo di interfaccia, è necessario annotare in modo esplicito il metodo come `SecurityCritical` o `SecuritySafeCritical`.</span><span class="sxs-lookup"><span data-stu-id="e4de9-154">If you override a virtual or abstract method or implement an interface method, you must explicitly annotate the method as `SecurityCritical` or `SecuritySafeCritical`.</span></span>|<span data-ttu-id="e4de9-155">Tutto il codice è Transparent per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="e4de9-155">All code defaults to transparent.</span></span> <span data-ttu-id="e4de9-156">I singoli tipi e membri possono tuttavia avere altri attributi.</span><span class="sxs-lookup"><span data-stu-id="e4de9-156">However, individual types and members can have other attributes.</span></span>|

### <a name="type-and-member-annotation"></a><span data-ttu-id="e4de9-157">Annotazione dei tipi e dei membri</span><span class="sxs-lookup"><span data-stu-id="e4de9-157">Type and Member Annotation</span></span>

<span data-ttu-id="e4de9-158">Gli attributi di sicurezza applicati a un tipo si applicano anche ai membri introdotti dal tipo.</span><span class="sxs-lookup"><span data-stu-id="e4de9-158">The security attributes that are applied to a type also apply to the members that are introduced by the type.</span></span> <span data-ttu-id="e4de9-159">Non si applicano tuttavia a override virtuali o astratti della classe base o delle implementazioni dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="e4de9-159">However, they do not apply to virtual or abstract overrides of the base class or interface implementations.</span></span> <span data-ttu-id="e4de9-160">Le regole seguenti si applicano all'uso degli attributi a livello di tipo e membro:</span><span class="sxs-lookup"><span data-stu-id="e4de9-160">The following rules apply to the use of attributes at the type and member level:</span></span>

- <span data-ttu-id="e4de9-161">`SecurityCritical`: il tipo o il membro è Critical e può essere chiamato solo da codice con attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="e4de9-161">`SecurityCritical`: The type or member is critical and can be called only by full-trust code.</span></span> <span data-ttu-id="e4de9-162">I metodi introdotti in un tipo SecurityCritical sono Critical.</span><span class="sxs-lookup"><span data-stu-id="e4de9-162">Methods that are introduced in a security-critical type are critical.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="e4de9-163">I metodi virtuali e astratti introdotti in classi base o interfacce e sottoposti a override o implementati in una classe SecurityCritical sono Transparent per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="e4de9-163">Virtual and abstract methods that are introduced in base classes or interfaces, and overridden or implemented in a security-critical class are transparent by default.</span></span> <span data-ttu-id="e4de9-164">Devono essere identificati come `SecuritySafeCritical` o `SecurityCritical`.</span><span class="sxs-lookup"><span data-stu-id="e4de9-164">They must be identified as either `SecuritySafeCritical` or `SecurityCritical`.</span></span>

- <span data-ttu-id="e4de9-165">`SecuritySafeCritical`: il tipo o il membro è SafeCritical.</span><span class="sxs-lookup"><span data-stu-id="e4de9-165">`SecuritySafeCritical`: The type or member is safe-critical.</span></span> <span data-ttu-id="e4de9-166">Il tipo o il membro può tuttavia essere chiamato da codice Transparent (parzialmente attendibile) e funziona come qualsiasi altro codice Critical.</span><span class="sxs-lookup"><span data-stu-id="e4de9-166">However, the type or member can be called from transparent (partially trusted) code and is as capable as any other critical code.</span></span> <span data-ttu-id="e4de9-167">Il codice deve essere controllato per garantirne la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="e4de9-167">The code must be audited for security.</span></span>

## <a name="override-patterns"></a><span data-ttu-id="e4de9-168">Criteri di override</span><span class="sxs-lookup"><span data-stu-id="e4de9-168">Override Patterns</span></span>

<span data-ttu-id="e4de9-169">Nella tabella seguente vengono elencati gli override dei metodi consentiti per la trasparenza di livello 2.</span><span class="sxs-lookup"><span data-stu-id="e4de9-169">The following table shows the method overrides allowed for level 2 transparency.</span></span>

|<span data-ttu-id="e4de9-170">Membro di base virtuale/di interfaccia</span><span class="sxs-lookup"><span data-stu-id="e4de9-170">Base virtual/interface member</span></span>|<span data-ttu-id="e4de9-171">Override/interfaccia</span><span class="sxs-lookup"><span data-stu-id="e4de9-171">Override/interface</span></span>|
|------------------------------------|-------------------------|
|`Transparent`|`Transparent`|
|`Transparent`|`SafeCritical`|
|`SafeCritical`|`Transparent`|
|`SafeCritical`|`SafeCritical`|
|`Critical`|`Critical`|

## <a name="inheritance-rules"></a><span data-ttu-id="e4de9-172">Regole di ereditarietà</span><span class="sxs-lookup"><span data-stu-id="e4de9-172">Inheritance Rules</span></span>

<span data-ttu-id="e4de9-173">In questa sezione, l'ordine seguente è assegnato al codice `Transparent`, `Critical` e `SafeCritical` in base all'accesso e alle funzionalità: </span><span class="sxs-lookup"><span data-stu-id="e4de9-173">In this section, the following order is assigned to `Transparent`, `Critical`, and `SafeCritical` code based on access and capabilities:</span></span>

`Transparent` < `SafeCritical` < `Critical`

- <span data-ttu-id="e4de9-174">Regole per i tipi: da sinistra verso destra l'accesso diventa più restrittivo.</span><span class="sxs-lookup"><span data-stu-id="e4de9-174">Rules for types: Going from left to right, access becomes more restrictive.</span></span> <span data-ttu-id="e4de9-175">I tipi derivati devono essere restrittivi almeno quanto il tipo di base.</span><span class="sxs-lookup"><span data-stu-id="e4de9-175">Derived types must be at least as restrictive as the base type.</span></span>

- <span data-ttu-id="e4de9-176">Regole per i metodi: i metodi derivati non possono modificare l'accessibilità dal metodo di base.</span><span class="sxs-lookup"><span data-stu-id="e4de9-176">Rules for methods: Derived methods cannot change accessibility from the base method.</span></span> <span data-ttu-id="e4de9-177">Per il comportamento predefinito, tutti i metodi derivati non annotati sono `Transparent`.</span><span class="sxs-lookup"><span data-stu-id="e4de9-177">For default behavior, all derived methods that are not annotated are `Transparent`.</span></span> <span data-ttu-id="e4de9-178">I derivati di tipi Critical provocano un'eccezione se il metodo sottoposto a override non è annotato in modo esplicito come `SecurityCritical`.</span><span class="sxs-lookup"><span data-stu-id="e4de9-178">Derivatives of critical types cause an exception to be thrown if the overridden method is not explicitly annotated as `SecurityCritical`.</span></span>

<span data-ttu-id="e4de9-179">Nella tabella seguente vengono elencati i criteri dell'ereditarietà dei tipi consentiti.</span><span class="sxs-lookup"><span data-stu-id="e4de9-179">The following table shows the allowed type inheritance patterns.</span></span>

|<span data-ttu-id="e4de9-180">Classe di base</span><span class="sxs-lookup"><span data-stu-id="e4de9-180">Base class</span></span>|<span data-ttu-id="e4de9-181">La classe derivata può essere</span><span class="sxs-lookup"><span data-stu-id="e4de9-181">Derived class can be</span></span>|
|----------------|--------------------------|
|`Transparent`|`Transparent`|
|`Transparent`|`SafeCritical`|
|`Transparent`|`Critical`|
|`SafeCritical`|`SafeCritical`|
|`SafeCritical`|`Critical`|
|`Critical`|`Critical`|

<span data-ttu-id="e4de9-182">Nella tabella seguente vengono elencati i criteri di ereditarietà dei tipi non consentiti.</span><span class="sxs-lookup"><span data-stu-id="e4de9-182">The following table shows the disallowed type inheritance patterns.</span></span>

|<span data-ttu-id="e4de9-183">Classe di base</span><span class="sxs-lookup"><span data-stu-id="e4de9-183">Base class</span></span>|<span data-ttu-id="e4de9-184">La classe derivata non può essere</span><span class="sxs-lookup"><span data-stu-id="e4de9-184">Derived class cannot be</span></span>|
|----------------|-----------------------------|
|`SafeCritical`|`Transparent`|
|`Critical`|`Transparent`|
|`Critical`|`SafeCritical`|

<span data-ttu-id="e4de9-185">Nella tabella seguente vengono elencati i criteri di ereditarietà dei metodi consentiti.</span><span class="sxs-lookup"><span data-stu-id="e4de9-185">The following table shows the allowed method inheritance patterns.</span></span>

|<span data-ttu-id="e4de9-186">Metodo di base</span><span class="sxs-lookup"><span data-stu-id="e4de9-186">Base method</span></span>|<span data-ttu-id="e4de9-187">Il metodo derivato può essere</span><span class="sxs-lookup"><span data-stu-id="e4de9-187">Derived method can be</span></span>|
|-----------------|---------------------------|
|`Transparent`|`Transparent`|
|`Transparent`|`SafeCritical`|
|`SafeCritical`|`Transparent`|
|`SafeCritical`|`SafeCritical`|
|`Critical`|`Critical`|

<span data-ttu-id="e4de9-188">Nella tabella seguente vengono elencati i criteri di ereditarietà dei metodi non consentiti.</span><span class="sxs-lookup"><span data-stu-id="e4de9-188">The following table shows the disallowed method inheritance patterns.</span></span>

|<span data-ttu-id="e4de9-189">Metodo di base</span><span class="sxs-lookup"><span data-stu-id="e4de9-189">Base method</span></span>|<span data-ttu-id="e4de9-190">Il metodo derivato non può essere</span><span class="sxs-lookup"><span data-stu-id="e4de9-190">Derived method cannot be</span></span>|
|-----------------|------------------------------|
|`Transparent`|`Critical`|
|`SafeCritical`|`Critical`|
|`Critical`|`Transparent`|
|`Critical`|`SafeCritical`|

> [!NOTE]
> <span data-ttu-id="e4de9-191">Queste regole di ereditarietà si applicano a tipi e membri di livello 2.</span><span class="sxs-lookup"><span data-stu-id="e4de9-191">These inheritance rules apply to level 2 types and members.</span></span> <span data-ttu-id="e4de9-192">I tipi di assembly di livello 1 possono ereditare dai membri e dai tipi SecurityCritical di livello 2.</span><span class="sxs-lookup"><span data-stu-id="e4de9-192">Types in level 1 assemblies can inherit from level 2 security-critical types and members.</span></span> <span data-ttu-id="e4de9-193">Pertanto, i tipi e i membri di livello 2 devono disporre di richieste di ereditarietà separate per gli eredi di livello 1.</span><span class="sxs-lookup"><span data-stu-id="e4de9-193">Therefore, level 2 types and members must have separate inheritance demands for level 1 inheritors.</span></span>

## <a name="additional-information-and-rules"></a><span data-ttu-id="e4de9-194">Informazioni e regole aggiuntive</span><span class="sxs-lookup"><span data-stu-id="e4de9-194">Additional Information and Rules</span></span>

### <a name="linkdemand-support"></a><span data-ttu-id="e4de9-195">Supporto LinkDemand</span><span class="sxs-lookup"><span data-stu-id="e4de9-195">LinkDemand Support</span></span>

<span data-ttu-id="e4de9-196">Nel modello di trasparenza di livello 2, <xref:System.Security.Permissions.SecurityAction.LinkDemand> è stato sostituito dall'attributo <xref:System.Security.SecurityCriticalAttribute>.</span><span class="sxs-lookup"><span data-stu-id="e4de9-196">The level 2 transparency model replaces the <xref:System.Security.Permissions.SecurityAction.LinkDemand> with the <xref:System.Security.SecurityCriticalAttribute> attribute.</span></span> <span data-ttu-id="e4de9-197">Nel codice legacy (livello 1), <xref:System.Security.Permissions.SecurityAction.LinkDemand> viene trattato automaticamente come <xref:System.Security.Permissions.SecurityAction.Demand>.</span><span class="sxs-lookup"><span data-stu-id="e4de9-197">In legacy (level 1) code, a <xref:System.Security.Permissions.SecurityAction.LinkDemand> is automatically treated as a <xref:System.Security.Permissions.SecurityAction.Demand>.</span></span>

### <a name="reflection"></a><span data-ttu-id="e4de9-198">Reflection</span><span class="sxs-lookup"><span data-stu-id="e4de9-198">Reflection</span></span>

<span data-ttu-id="e4de9-199">Se si richiama un metodo Critical o si legge un campo Critical, viene generata una richiesta di attendibilità totale, come se si stesse richiamando un metodo o un campo Private.</span><span class="sxs-lookup"><span data-stu-id="e4de9-199">Invoking a critical method or reading a critical field triggers a demand for full trust (just as if you were invoking a private method or field).</span></span> <span data-ttu-id="e4de9-200">Il codice con attendibilità totale può quindi richiamare un metodo Critical, a differenza del codice parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="e4de9-200">Therefore, full-trust code can invoke a critical method, whereas partial-trust code cannot.</span></span>

<span data-ttu-id="e4de9-201">Le proprietà seguenti sono state aggiunte allo spazio dei nomi di <xref:System.Reflection> per determinare se il tipo, il metodo, o il campo è `SecurityCritical`, `SecuritySafeCritical` o `SecurityTransparent`: <xref:System.Type.IsSecurityCritical%2A>, <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A> e <xref:System.Reflection.MethodBase.IsSecurityTransparent%2A>.</span><span class="sxs-lookup"><span data-stu-id="e4de9-201">The following properties have been added to the <xref:System.Reflection> namespace to determine whether the type, method, or field is `SecurityCritical`, `SecuritySafeCritical`, or `SecurityTransparent`:  <xref:System.Type.IsSecurityCritical%2A>, <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A>, and <xref:System.Reflection.MethodBase.IsSecurityTransparent%2A>.</span></span> <span data-ttu-id="e4de9-202">Usare queste proprietà per determinare la trasparenza con reflection anziché verificare la presenza dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="e4de9-202">Use these properties to determine transparency by using reflection instead of checking for the presence of the attribute.</span></span> <span data-ttu-id="e4de9-203">Le regole di trasparenza sono complesse ed la verifica dell'attributo potrebbe non essere sufficiente.</span><span class="sxs-lookup"><span data-stu-id="e4de9-203">The transparency rules are complex, and checking for the attribute may not be sufficient.</span></span>

> [!NOTE]
> <span data-ttu-id="e4de9-204">Un `SafeCritical` metodo restituisce `true` sia per sia per <xref:System.Type.IsSecurityCritical%2A> <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A> , perché `SafeCritical` è effettivamente critico (presenta le stesse funzionalità del codice critico, ma può essere chiamato dal codice trasparente).</span><span class="sxs-lookup"><span data-stu-id="e4de9-204">A `SafeCritical` method returns `true` for both <xref:System.Type.IsSecurityCritical%2A> and <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A>, because `SafeCritical` is indeed critical (it has the same capabilities as critical code, but it can be called from transparent code).</span></span>

<span data-ttu-id="e4de9-205">I metodi dinamici ereditano la trasparenza dei moduli a cui sono allegati, mentre non ereditano la trasparenza del tipo, nel caso in cui siano allegati a un tipo.</span><span class="sxs-lookup"><span data-stu-id="e4de9-205">Dynamic methods inherit the transparency of the modules they are attached to; they do not inherit the transparency of the type (if they are attached to a type).</span></span>

### <a name="skip-verification-in-full-trust"></a><span data-ttu-id="e4de9-206">Ignorare la verifica in attendibilità totale</span><span class="sxs-lookup"><span data-stu-id="e4de9-206">Skip Verification in Full Trust</span></span>

<span data-ttu-id="e4de9-207">È possibile ignorare la verifica degli assembly Transparent completamente attendibili impostando la proprietà <xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A> su `true` nell'attributo <xref:System.Security.SecurityRulesAttribute>:</span><span class="sxs-lookup"><span data-stu-id="e4de9-207">You can skip verification for fully trusted transparent assemblies by setting the <xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A> property to `true` in the <xref:System.Security.SecurityRulesAttribute> attribute:</span></span>

`[assembly: SecurityRules(SecurityRuleSet.Level2, SkipVerificationInFullTrust = true)]`

<span data-ttu-id="e4de9-208">La proprietà <xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A> è `false`e per impostazione predefinita, quindi deve essere impostata su `true` per ignorare la verifica.</span><span class="sxs-lookup"><span data-stu-id="e4de9-208">The <xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A> property is `false` by default, so the property must be set to `true` to skip verification.</span></span> <span data-ttu-id="e4de9-209">Questa operazione deve essere eseguita solo per ottimizzare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="e4de9-209">This should be done for optimization purposes only.</span></span> <span data-ttu-id="e4de9-210">È necessario assicurarsi che il codice Transparent nell'assembly sia verificabile tramite l' `transparent` opzione nello [strumento PEVerify](../tools/peverify-exe-peverify-tool.md).</span><span class="sxs-lookup"><span data-stu-id="e4de9-210">You should ensure that the transparent code in the assembly is verifiable by using the `transparent` option in the [PEVerify tool](../tools/peverify-exe-peverify-tool.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e4de9-211">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4de9-211">See also</span></span>

- [<span data-ttu-id="e4de9-212">Codice SecurityTransparent, livello 1</span><span class="sxs-lookup"><span data-stu-id="e4de9-212">Security-Transparent Code, Level 1</span></span>](security-transparent-code-level-1.md)
- [<span data-ttu-id="e4de9-213">Modifiche della sicurezza</span><span class="sxs-lookup"><span data-stu-id="e4de9-213">Security Changes</span></span>](https://docs.microsoft.com/previous-versions/dotnet/framework/security/security-changes)
