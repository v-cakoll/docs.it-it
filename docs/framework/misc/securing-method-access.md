---
title: Protezione dell'accesso ai metodi
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
ms.openlocfilehash: a9e1226483eaa02dc8dc3dfb741e3df6b2985fbe
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181149"
---
# <a name="securing-method-access"></a>Protezione dell'accesso ai metodi
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 Alcuni metodi potrebbero non essere adatti per consentire le chiamate da parte di codice non attendibile arbitrario. Tali metodi comportano diversi rischi: il metodo può fornire informazioni riservate; può ritenere valide tutte le informazioni passate; può non controllare gli errori sui parametri; con i parametri non corretti, potrebbe presentare problemi di funzionamento o causare danni. L'utente dovrebbe essere informato di questi casi e adottare le misure appropriate per proteggere il metodo.  
  
 In alcuni casi, potrebbe essere necessario limitare i metodi che non sono destinati all'uso pubblico, ma che devono comunque essere pubblici; ad esempio, nel caso di un'interfaccia che deve essere chiamata attraverso le proprie DLL e pertanto deve essere pubblica, ma che non si vuole esporre pubblicamente per evitare che i clienti la usino oppure per impedire che il codice dannoso sfrutti il punto di ingresso al componente. Un altro motivo comune per limitare un metodo non destinato all'uso pubblico (ma che deve essere pubblico) consiste nell'evitare di dover documentare e supportare quella che potrebbe essere un'interfaccia molto interna.  
  
 Il codice gestito offre diversi modi per limitare l'accesso ai metodi:  
  
- Limitare l'ambito di accessibilità alla classe, all'assembly o alle classi derivate, se possono essere attendibili. Questo è il modo più semplice per limitare l'accesso del metodo. Si noti che, in generale, le classi derivate possono essere meno affidabili rispetto alla classe da cui derivano, anche se in alcuni casi condividono l'identità della classe padre. In particolare, non dedurre l'attendibilità dalla parola chiave **protected**, che non viene necessariamente utilizzata nel contesto di sicurezza.  
  
- Limitare l'accesso al metodo ai chiamanti di un'identità specificata, essenzialmente qualsiasi [prova](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7y5x1hcd%28v=vs.100%29) particolare (nome sicuro, editore, zona e così via) scelta.  
  
- Limitare l'accesso al metodo ai chiamanti che dispongono delle autorizzazioni selezionate.  
  
 Analogamente, la sicurezza dichiarativa consente di controllare l'ereditarietà delle classi. È possibile utilizzare InheritanceDemand per eseguire le operazioni seguenti:You can use **InheritanceDemand** to do the following:  
  
- Richiedere le classi derivate per ottenere un'identità o autorizzazione specificata.  
  
- Richiedere le classi derivate che eseguono l'override di metodi specifici per ottenere un'identità o autorizzazione specificata.  
  
 L'esempio seguente illustra come proteggere una classe pubblica per l'accesso limitato richiedendo che i chiamanti siano firmati con un nome sicuro specifico. In questo <xref:System.Security.Permissions.StrongNameIdentityPermissionAttribute> esempio viene utilizzato l'oggetto con una **richiesta** per il nome sicuro. Per informazioni su attività su come firmare un assembly con un nome sicuro, vedere Creazione e utilizzo di [assembly con nome sicuro](../../standard/assembly/create-use-strong-named.md).  
  
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
  
## <a name="excluding-classes-and-members-from-use-by-untrusted-code"></a>Esclusione di classi e membri dall'utilizzo da parte di codice non attendibile  
 Usare le dichiarazioni illustrate in questa sezione per impedire l'uso di specifiche classi e metodi, nonché proprietà ed eventi, da parte di codice parzialmente attendibile. Applicando tali dichiarazioni a una classe, è possibile applicare la protezione a tutti i relativi metodi, proprietà ed eventi. Si noti tuttavia che l'accesso al campo non è influenzato dalla protezione dichiarativa. Si noti inoltre che le richieste di collegamento aiutano a proteggere solo dai chiamanti immediati e potrebbero essere comunque soggette ad attacchi.  
  
> [!NOTE]
> È stato introdotto un nuovo modello di trasparenza in .NET Framework 4. Il modello [Security-Transparent Code, Level](security-transparent-code-level-2.md) 2 <xref:System.Security.SecurityCriticalAttribute> identifica il codice sicuro con l'attributo. Il codice critico per la sicurezza richiede che chiamanti ed eredi siano completamente attendibili. Gli assembly in esecuzione con le regole di protezione dell'accesso al codice delle versioni precedenti di .NET Framework possono chiamare gli assembly di livello 2. In questo caso, gli attributi critici per la sicurezza verranno considerati come richieste di collegamento per l'attendibilità totale.  
  
 Negli assembly con nome sicuro, un [LinkDemand](link-demands.md) viene applicato a tutti i metodi, le proprietà e gli eventi accessibili pubblicamente per limitarne l'utilizzo ai chiamanti completamente attendibili. Per disabilitare questa funzionalità, è necessario applicare l'attributo <xref:System.Security.AllowPartiallyTrustedCallersAttribute>. Di conseguenza, contrassegnare esplicitamente le classi in modo da escludere i chiamanti non attendibili è necessario solo per gli assembly non firmati oppure per gli assembly con questo attributo. È possibile usare queste dichiarazioni per contrassegnare un sottoinsieme di tipi non destinati a chiamanti non attendibili.  
  
 Gli esempi seguenti illustrano come impedire l'uso di classi e membri da parte di codice non attendibile.  
  
 Per le classi non sealed pubbliche:  
  
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
  
 Per le classi sealed pubbliche:  
  
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
  
 Per le classi astratte pubbliche:  
  
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
  
 Per le funzioni virtuali pubbliche:  
  
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
  
 Per le funzioni astratte pubbliche:  
  
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
  
 Per le funzioni pubbliche di override in cui la classe di base non richiede l'attendibilità totale:  
  
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
  
 Per le funzioni pubbliche di override in cui la classe di base richiede l'attendibilità totale:  
  
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
  
 Per le interfacce pubbliche:  
  
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
  
## <a name="virtual-internal-overrides-or-overloads-overridable-friend"></a>Override virtual interni e friend sottoponibile a override da overload  
  
> [!NOTE]
> In questa sezione viene visualizzato un avviso relativo `internal` `Overloads` `Overridable` a un problema di sicurezza quando si dichiara un metodo come entrambi `Friend` `virtual` e ( in Visual Basic). Questo avviso si applica solo a .NET Framework versioni 1.0 e 1.1, non si applica alle versioni successive.  
  
 In .NET Framework versioni 1.0 e 1.1, è necessario essere consapevoli di una sfumatura dell'accessibilità del sistema di tipi quando si conferma che il codice non è disponibile per altri assembly. Un metodo dichiarato **virtual** e **internal** **(Overloads Overridable Friend** in Visual Basic) può eseguire l'override della voce vtable della classe padre e può essere utilizzato solo dall'interno dello stesso assembly perché è interno. Tuttavia, l'accessibilità per l'override è determinata dalla parola chiave **virtual** e può essere sottoposta a override da un altro assembly, purché tale codice abbia accesso alla classe stessa. Se la possibilità di un override presenta un problema, utilizzare la sicurezza dichiarativa per risolverlo o rimuovere la parola chiave **virtual** se non è strettamente necessaria.  
  
 Si noti che anche se un compilatore di linguaggio impedisce questi override con un errore di compilazione, è possibile eseguire l'override per il codice scritto con altri compilatori.  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida per la generazione di codice sicuro](../../standard/security/secure-coding-guidelines.md)
