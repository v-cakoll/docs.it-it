---
title: Protezione dell'accesso ai metodi
description: Informazioni su come rendere sicuro l'accesso al metodo per i metodi che non sono destinati all'uso pubblico, ma che devono comunque essere pubblici.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- code security, method access
- secure coding, method access
- security [.NET Framework], method access
- method access security
ms.assetid: f7c2d6ec-3b18-4e0e-9991-acd97189d818
ms.openlocfilehash: a7ef419cf3959cf7a3ffde874353dacd3815c81a
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309391"
---
# <a name="securing-method-access"></a><span data-ttu-id="707d1-103">Protezione dell'accesso ai metodi</span><span class="sxs-lookup"><span data-stu-id="707d1-103">Securing Method Access</span></span>
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 <span data-ttu-id="707d1-104">Alcuni metodi potrebbero non essere adatti per consentire le chiamate da parte di codice non attendibile arbitrario.</span><span class="sxs-lookup"><span data-stu-id="707d1-104">Some methods might not be suitable to allow arbitrary untrusted code to call.</span></span> <span data-ttu-id="707d1-105">Tali metodi comportano diversi rischi: il metodo può fornire informazioni riservate; può ritenere valide tutte le informazioni passate; può non controllare gli errori sui parametri; con i parametri non corretti, potrebbe presentare problemi di funzionamento o causare danni.</span><span class="sxs-lookup"><span data-stu-id="707d1-105">Such methods pose several risks: The method might provide some restricted information; it might believe any information passed to it; it might not do error checking on the parameters; or with the wrong parameters, it might malfunction or do something harmful.</span></span> <span data-ttu-id="707d1-106">L'utente dovrebbe essere informato di questi casi e adottare le misure appropriate per proteggere il metodo.</span><span class="sxs-lookup"><span data-stu-id="707d1-106">You should be aware of these cases and take action to help protect the method.</span></span>  
  
 <span data-ttu-id="707d1-107">In alcuni casi, potrebbe essere necessario limitare i metodi che non sono destinati all'uso pubblico, ma che devono comunque essere pubblici;</span><span class="sxs-lookup"><span data-stu-id="707d1-107">In some cases, you might need to restrict methods that are not intended for public use but still must be public.</span></span> <span data-ttu-id="707d1-108">ad esempio, nel caso di un'interfaccia che deve essere chiamata attraverso le proprie DLL e pertanto deve essere pubblica, ma che non si vuole esporre pubblicamente per evitare che i clienti la usino oppure per impedire che il codice dannoso sfrutti il punto di ingresso al componente.</span><span class="sxs-lookup"><span data-stu-id="707d1-108">For example, you might have an interface that needs to be called across your own DLLs and hence must be public, but you do not want to expose it publicly to prevent customers from using it or to prevent malicious code from exploiting the entry point into your component.</span></span> <span data-ttu-id="707d1-109">Un altro motivo comune per limitare un metodo non destinato all'uso pubblico (ma che deve essere pubblico) consiste nell'evitare di dover documentare e supportare quello che potrebbe essere un'interfaccia interna.</span><span class="sxs-lookup"><span data-stu-id="707d1-109">Another common reason to restrict a method not intended for public use (but that must be public) is to avoid having to document and support what might be an internal interface.</span></span>  
  
 <span data-ttu-id="707d1-110">Il codice gestito offre diversi modi per limitare l'accesso ai metodi:</span><span class="sxs-lookup"><span data-stu-id="707d1-110">Managed code offers several ways to restrict method access:</span></span>  
  
- <span data-ttu-id="707d1-111">Limitare l'ambito di accessibilità alla classe, all'assembly o alle classi derivate, se possono essere attendibili.</span><span class="sxs-lookup"><span data-stu-id="707d1-111">Limit the scope of accessibility to the class, assembly, or derived classes, if they can be trusted.</span></span> <span data-ttu-id="707d1-112">Questo è il modo più semplice per limitare l'accesso del metodo.</span><span class="sxs-lookup"><span data-stu-id="707d1-112">This is the simplest way to limit method access.</span></span> <span data-ttu-id="707d1-113">In generale, le classi derivate possono essere meno attendibili rispetto alla classe da cui derivano, anche se in alcuni casi condividono l'identità della classe padre.</span><span class="sxs-lookup"><span data-stu-id="707d1-113">In general, derived classes can be less trustworthy than the class they derive from, though in some cases they share the parent class's identity.</span></span> <span data-ttu-id="707d1-114">In particolare, non dedurre attendibilità dalla parola chiave `protected` , che non viene necessariamente utilizzata nel contesto di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="707d1-114">In particular, do not infer trust from the keyword `protected`, which is not necessarily used in the security context.</span></span>  
  
- <span data-ttu-id="707d1-115">Limitare l'accesso al metodo ai chiamanti di un'identità specificata, sostanzialmente, qualsiasi [evidenza](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7y5x1hcd%28v=vs.100%29) particolare (nome sicuro, autore, zona e così via) scelta.</span><span class="sxs-lookup"><span data-stu-id="707d1-115">Limit the method access to callers of a specified identity--essentially, any particular [evidence](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7y5x1hcd%28v=vs.100%29) (strong name, publisher, zone, and so on) you choose.</span></span>  
  
- <span data-ttu-id="707d1-116">Limitare l'accesso al metodo ai chiamanti che dispongono delle autorizzazioni selezionate.</span><span class="sxs-lookup"><span data-stu-id="707d1-116">Limit the method access to callers having whatever permissions you select.</span></span>  
  
 <span data-ttu-id="707d1-117">Analogamente, la sicurezza dichiarativa consente di controllare l'ereditarietà delle classi.</span><span class="sxs-lookup"><span data-stu-id="707d1-117">Similarly, declarative security allows you to control inheritance of classes.</span></span> <span data-ttu-id="707d1-118">È possibile usare **InheritanceDemand** per eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="707d1-118">You can use **InheritanceDemand** to do the following:</span></span>  
  
- <span data-ttu-id="707d1-119">Richiedere le classi derivate per ottenere un'identità o autorizzazione specificata.</span><span class="sxs-lookup"><span data-stu-id="707d1-119">Require derived classes to have a specified identity or permission.</span></span>  
  
- <span data-ttu-id="707d1-120">Richiedere le classi derivate che eseguono l'override di metodi specifici per ottenere un'identità o autorizzazione specificata.</span><span class="sxs-lookup"><span data-stu-id="707d1-120">Require derived classes that override specific methods to have a specified identity or permission.</span></span>  
  
 <span data-ttu-id="707d1-121">L'esempio seguente illustra come proteggere una classe pubblica per l'accesso limitato richiedendo che i chiamanti siano firmati con un nome sicuro specifico.</span><span class="sxs-lookup"><span data-stu-id="707d1-121">The following example shows how to help protect a public class for limited access by requiring that callers be signed with a particular strong name.</span></span> <span data-ttu-id="707d1-122">In questo esempio viene utilizzato <xref:System.Security.Permissions.StrongNameIdentityPermissionAttribute> con una **richiesta** per il nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="707d1-122">This example uses the <xref:System.Security.Permissions.StrongNameIdentityPermissionAttribute> with a **Demand** for the strong name.</span></span> <span data-ttu-id="707d1-123">Per informazioni basate su attività su come firmare un assembly con un nome sicuro, vedere [creazione e uso di assembly con nome sicuro](../../standard/assembly/create-use-strong-named.md).</span><span class="sxs-lookup"><span data-stu-id="707d1-123">For task-based information on how to sign an assembly with a strong name, see [Creating and Using Strong-Named Assemblies](../../standard/assembly/create-use-strong-named.md).</span></span>  
  
```vb  
<StrongNameIdentityPermissionAttribute(SecurityAction.Demand, PublicKey := "…hex…", Name := "App1", Version := "0.0.0.0")>  _  
Public Class Class1  
End Class  
```  
  
```csharp  
[StrongNameIdentityPermissionAttribute(SecurityAction.Demand, PublicKey="…hex…", Name="App1", Version="0.0.0.0")]  
public class Class1  
{  
  
}
```  
  
## <a name="excluding-classes-and-members-from-use-by-untrusted-code"></a><span data-ttu-id="707d1-124">Esclusione di classi e membri dall'utilizzo da parte di codice non attendibile</span><span class="sxs-lookup"><span data-stu-id="707d1-124">Excluding Classes and Members from Use by Untrusted Code</span></span>  
 <span data-ttu-id="707d1-125">Usare le dichiarazioni illustrate in questa sezione per impedire l'uso di specifiche classi e metodi, nonché proprietà ed eventi, da parte di codice parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="707d1-125">Use the declarations shown in this section to prevent specific classes and methods, as well as properties and events, from being used by partially trusted code.</span></span> <span data-ttu-id="707d1-126">Applicando queste dichiarazioni a una classe, si applica la protezione a tutti i relativi metodi, proprietà ed eventi.</span><span class="sxs-lookup"><span data-stu-id="707d1-126">By applying these declarations to a class, you apply the protection to all its methods, properties, and events.</span></span> <span data-ttu-id="707d1-127">Tuttavia, l'accesso al campo non è influenzato dalla sicurezza dichiarativa.</span><span class="sxs-lookup"><span data-stu-id="707d1-127">However, field access is not affected by declarative security.</span></span> <span data-ttu-id="707d1-128">Si noti inoltre che le richieste di collegamento aiutano a proteggere solo dai chiamanti immediati e potrebbero essere comunque soggette ad attacchi.</span><span class="sxs-lookup"><span data-stu-id="707d1-128">Note also that link demands help protect against only the immediate callers and might still be subject to luring attacks.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="707d1-129">In .NET Framework 4 è stato introdotto un nuovo modello di trasparenza.</span><span class="sxs-lookup"><span data-stu-id="707d1-129">A new transparency model has been introduced in the .NET Framework 4.</span></span> <span data-ttu-id="707d1-130">Il [codice SecurityTransparent,](security-transparent-code-level-2.md) il modello di livello 2 identifica il codice sicuro con l' <xref:System.Security.SecurityCriticalAttribute> attributo.</span><span class="sxs-lookup"><span data-stu-id="707d1-130">The [Security-Transparent Code, Level 2](security-transparent-code-level-2.md) model identifies secure code with the <xref:System.Security.SecurityCriticalAttribute> attribute.</span></span> <span data-ttu-id="707d1-131">Il codice critico per la sicurezza richiede che chiamanti ed eredi siano completamente attendibili.</span><span class="sxs-lookup"><span data-stu-id="707d1-131">Security-critical code requires both callers and inheritors to be fully trusted.</span></span> <span data-ttu-id="707d1-132">Gli assembly in esecuzione con le regole di protezione dell'accesso al codice delle versioni precedenti di .NET Framework possono chiamare gli assembly di livello 2.</span><span class="sxs-lookup"><span data-stu-id="707d1-132">Assemblies that are running under the code access security rules from earlier .NET Framework versions can call level 2 assemblies.</span></span> <span data-ttu-id="707d1-133">In questo caso, gli attributi critici per la sicurezza verranno considerati come richieste di collegamento per l'attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="707d1-133">In this case, the security-critical attributes will be treated as link demands for full trust.</span></span>  
  
 <span data-ttu-id="707d1-134">Negli assembly con nome sicuro, un [LinkDemand](link-demands.md) viene applicato a tutti i metodi, le proprietà e gli eventi accessibili pubblicamente per limitarne l'uso a chiamanti completamente attendibili.</span><span class="sxs-lookup"><span data-stu-id="707d1-134">In strong-named assemblies, a [LinkDemand](link-demands.md) is applied to all publicly accessible methods, properties, and events therein to restrict their use to fully trusted callers.</span></span> <span data-ttu-id="707d1-135">Per disabilitare questa funzionalità, è necessario applicare l'attributo <xref:System.Security.AllowPartiallyTrustedCallersAttribute>.</span><span class="sxs-lookup"><span data-stu-id="707d1-135">To disable this feature, you must apply the <xref:System.Security.AllowPartiallyTrustedCallersAttribute> attribute.</span></span> <span data-ttu-id="707d1-136">Di conseguenza, contrassegnare esplicitamente le classi in modo da escludere i chiamanti non attendibili è necessario solo per gli assembly non firmati oppure per gli assembly con questo attributo. È possibile usare queste dichiarazioni per contrassegnare un sottoinsieme di tipi non destinati a chiamanti non attendibili.</span><span class="sxs-lookup"><span data-stu-id="707d1-136">Thus, explicitly marking classes to exclude untrusted callers is necessary only for unsigned assemblies or assemblies with this attribute; you can use these declarations to mark a subset of types therein that are not intended for untrusted callers.</span></span>  
  
 <span data-ttu-id="707d1-137">Gli esempi seguenti illustrano come impedire l'uso di classi e membri da parte di codice non attendibile.</span><span class="sxs-lookup"><span data-stu-id="707d1-137">The following examples show how to prevent classes and members from being used by untrusted code.</span></span>  
  
 <span data-ttu-id="707d1-138">Per le classi non sealed pubbliche:</span><span class="sxs-lookup"><span data-stu-id="707d1-138">For public nonsealed classes:</span></span>  
  
```vb  
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name := "FullTrust"), _
System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name := "FullTrust")>  _  
Public Class CanDeriveFromMe  
End Class  
```  
  
```csharp  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name="FullTrust")]  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name="FullTrust")]  
public class CanDeriveFromMe  
{  
}  
```  
  
 <span data-ttu-id="707d1-139">Per le classi sealed pubbliche:</span><span class="sxs-lookup"><span data-stu-id="707d1-139">For public sealed classes:</span></span>  
  
```vb  
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name := "FullTrust")>  _  
NotInheritable Public Class CannotDeriveFromMe  
End Class  
```  
  
```csharp  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name="FullTrust")]  
public sealed class CannotDeriveFromMe  
{  
}  
```  
  
 <span data-ttu-id="707d1-140">Per le classi astratte pubbliche:</span><span class="sxs-lookup"><span data-stu-id="707d1-140">For public abstract classes:</span></span>  
  
```vb  
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name := "FullTrust"), _  
System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name := "FullTrust")>  _  
MustInherit Public Class CannotCreateInstanceOfMe_CanCastToMe  
End Class  
```  
  
```csharp  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name="FullTrust")]  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name="FullTrust")]  
public abstract class CannotCreateInstanceOfMe_CanCastToMe {}  
```  
  
 <span data-ttu-id="707d1-141">Per le funzioni virtuali pubbliche:</span><span class="sxs-lookup"><span data-stu-id="707d1-141">For public virtual functions:</span></span>  
  
```vb  
Class Base1
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name:="FullTrust"), System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name:="FullTrust")> _  
    Public Overridable Sub CanOverrideOrCallMe()  
    End Sub 'CanOverrideOrCallMe  
End Class 'Base1  
```  
  
```csharp  
class Base1
{  
[System.Security.Permissions.PermissionSetAttribute(  
System.Security.Permissions.SecurityAction.InheritanceDemand, Name="FullTrust")]  
[System.Security.Permissions.PermissionSetAttribute(  
System.Security.Permissions.SecurityAction.LinkDemand, Name="FullTrust")]  
    public virtual void CanOverrideOrCallMe() {}  
}  
```  
  
 <span data-ttu-id="707d1-142">Per le funzioni astratte pubbliche:</span><span class="sxs-lookup"><span data-stu-id="707d1-142">For public abstract functions:</span></span>  
  
```vb  
MustInherit Class Base2  
    <System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name:="FullTrust"), System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name:="FullTrust")> _  
    Public Sub MustOverrideMe()  
    End Sub  
End Class 'Base2  
```  
  
```csharp  
abstract class Base2 {  
[System.Security.Permissions.PermissionSetAttribute(  
System.Security.Permissions.SecurityAction.InheritanceDemand, Name = "FullTrust")]  
[System.Security.Permissions.PermissionSetAttribute(  
System.Security.Permissions.SecurityAction.LinkDemand, Name = "FullTrust")]  
public abstract void MustOverrideMe();  
}  
```  
  
 <span data-ttu-id="707d1-143">Per le funzioni pubbliche di override in cui la classe di base non richiede l'attendibilità totale:</span><span class="sxs-lookup"><span data-stu-id="707d1-143">For public override functions where the base class does not demand full trust:</span></span>  
  
```vb  
Class Derived  
    Inherits Base1  
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.Demand, Name:="FullTrust")> _  
    Public Overrides Sub CanOverrideOrCallMe()  
        MyBase.CanOverrideOrCallMe()  
    End Sub 'CanOverrideOrCallMe  
End Class 'Derived  
```  
  
```csharp  
class Derived : Base1  
{
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.Demand, Name="FullTrust")]
    public override void CanOverrideOrCallMe()
    {  
        base.CanOverrideOrCallMe();  
    }  
}  
```  
  
 <span data-ttu-id="707d1-144">Per le funzioni pubbliche di override in cui la classe di base richiede l'attendibilità totale:</span><span class="sxs-lookup"><span data-stu-id="707d1-144">For public override functions where the base class demands full trust:</span></span>  
  
```vb  
Class Derived  
    Inherits Base1  
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name:="FullTrust")> _  
    Public Overrides Sub CanOverrideOrCallMe()  
        MyBase.CanOverrideOrCallMe()  
    End Sub 'CanOverrideOrCallMe
End Class 'Derived  
```  
  
```csharp  
class Derived : Base1  
{
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name="FullTrust")]
    public override void CanOverrideOrCallMe()
    {  
        base.CanOverrideOrCallMe();  
    }  
}  
```  
  
 <span data-ttu-id="707d1-145">Per le interfacce pubbliche:</span><span class="sxs-lookup"><span data-stu-id="707d1-145">For public interfaces:</span></span>  
  
```vb  
Public Interface ICanCastToMe  
    <System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name:="FullTrust"), System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name:="FullTrust")> _  
    Sub CanImplementMe()  
End Interface 'ICanCastToMe  
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name:="FullTrust"), System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name:="FullTrust")> _  
Class Implemented  
    Implements ICanCastToMe  
    Public Sub CanImplementMe()  
    End Sub 'CanImplementMe  
```  
  
```csharp  
public interface ICanCastToMe
{  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name = "FullTrust")]  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name = "FullTrust")]  
void CanImplementMe();  
}  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name = "FullTrust")]  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name = "FullTrust")]  
class Implemented : ICanCastToMe  
{  
    public void CanImplementMe()  
    {  
    }  
}  
```  
  
## <a name="virtual-internal-overrides-or-overloads-overridable-friend"></a><span data-ttu-id="707d1-146">Override virtual interni e friend sottoponibile a override da overload</span><span class="sxs-lookup"><span data-stu-id="707d1-146">Virtual Internal Overrides or Overloads Overridable Friend</span></span>  
  
> [!NOTE]
> <span data-ttu-id="707d1-147">In questa sezione viene visualizzato un avviso relativo a un problema di sicurezza quando si dichiara un metodo come `virtual` e `internal` ( `Overloads` `Overridable` `Friend` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="707d1-147">This section warns about a security issue when declaring a method as both `virtual` and `internal` (`Overloads` `Overridable` `Friend` in Visual Basic).</span></span> <span data-ttu-id="707d1-148">Questo avviso si applica solo alle versioni .NET Framework 1,0 e 1,1, ma non a versioni successive.</span><span class="sxs-lookup"><span data-stu-id="707d1-148">This warning applies only to the .NET Framework versions 1.0 and 1.1, it does not apply to later versions.</span></span>  
  
 <span data-ttu-id="707d1-149">Nelle versioni .NET Framework 1,0 e 1,1, è necessario essere a conoscenza di una sfumatura dell'accessibilità del sistema di tipi quando si conferma che il codice non è disponibile per altri assembly.</span><span class="sxs-lookup"><span data-stu-id="707d1-149">In the .NET Framework versions 1.0 and 1.1, you must be aware of a nuance of the type system accessibility when confirming that your code is unavailable to other assemblies.</span></span> <span data-ttu-id="707d1-150">Un metodo dichiarato **virtuale** e **interno** (che esegue l'overload di un elemento**Friend** in Visual Basic) può eseguire l'override della voce vtable della classe padre e può essere utilizzato solo dall'interno dello stesso assembly perché è interno.</span><span class="sxs-lookup"><span data-stu-id="707d1-150">A method that is declared **virtual** and **internal** (**Overloads Overridable Friend** in Visual Basic) can override the parent class's vtable entry and can be used only from within the same assembly because it is internal.</span></span> <span data-ttu-id="707d1-151">Tuttavia, l'accessibilità per l'override è determinata dalla parola chiave **Virtual** , che può essere sottoposta a override da un altro assembly, purché tale codice possa accedere alla classe stessa.</span><span class="sxs-lookup"><span data-stu-id="707d1-151">However, the accessibility for overriding is determined by the **virtual** keyword, and this can be overridden from another assembly as long as that code has access to the class itself.</span></span> <span data-ttu-id="707d1-152">Se la possibilità di un override presenta un problema, usare la sicurezza dichiarativa per correggerla o rimuovere la parola chiave **Virtual** se non è strettamente necessaria.</span><span class="sxs-lookup"><span data-stu-id="707d1-152">If the possibility of an override presents a problem, use declarative security to fix it, or remove the **virtual** keyword if it is not strictly required.</span></span>  
  
 <span data-ttu-id="707d1-153">Anche se un compilatore di linguaggio impedisce tali sostituzioni con un errore di compilazione, è possibile che il codice scritto con altri compilatori esegua l'override.</span><span class="sxs-lookup"><span data-stu-id="707d1-153">Even if a language compiler prevents these overrides with a compilation error, it is possible for code written with other compilers to override.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="707d1-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="707d1-154">See also</span></span>

- [<span data-ttu-id="707d1-155">Linee guida per la generazione di codice sicuro</span><span class="sxs-lookup"><span data-stu-id="707d1-155">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)
