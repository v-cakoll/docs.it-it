---
title: 'Procedura: creare un oggetto WindowsPrincipal'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WindowsPrincipal objects, creating
- security [.NET Framework], creating a WindowsPrincipal object
- security [.NET Framework], principals
- principal objects, creating
ms.assetid: 56eb10ca-e61d-4ed2-af7a-555fc4c25a25
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 016f19c7141ebaf9b5c1f03adc263b689489119b
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2018
ms.locfileid: "44198036"
---
# <a name="how-to-create-a-windowsprincipal-object"></a><span data-ttu-id="4ccfc-102">Procedura: creare un oggetto WindowsPrincipal</span><span class="sxs-lookup"><span data-stu-id="4ccfc-102">How to: Create a WindowsPrincipal Object</span></span>
<span data-ttu-id="4ccfc-103">Vi sono due metodi per creare un oggetto <xref:System.Security.Principal.WindowsPrincipal>, a seconda che il codice debba eseguire ripetutamente la convalida basata sui ruoli o solo una alla volta.</span><span class="sxs-lookup"><span data-stu-id="4ccfc-103">There are two ways to create a <xref:System.Security.Principal.WindowsPrincipal> object, depending on whether code must repeatedly perform role-based validation or must perform it only once.</span></span>  
  
 <span data-ttu-id="4ccfc-104">Se è necessario che il codice esegua ripetutamente la convalida basata sui ruoli, la prima delle procedure riportate di seguito implica un minor sovraccarico.</span><span class="sxs-lookup"><span data-stu-id="4ccfc-104">If code must repeatedly perform role-based validation, the first of the following procedures produces less overhead.</span></span> <span data-ttu-id="4ccfc-105">Quando è necessario che il codice esegua convalide basate sui ruoli solo una volta, è possibile creare un oggetto <xref:System.Security.Principal.WindowsPrincipal> usando la seconda delle seguenti procedure.</span><span class="sxs-lookup"><span data-stu-id="4ccfc-105">When code needs to make role-based validations only once, you can create a <xref:System.Security.Principal.WindowsPrincipal> object by using the second of the following procedures.</span></span>  
  
### <a name="to-create-a-windowsprincipal-object-for-repeated-validation"></a><span data-ttu-id="4ccfc-106">Per creare un oggetto WindowsPrincipal per una convalida ripetuta</span><span class="sxs-lookup"><span data-stu-id="4ccfc-106">To create a WindowsPrincipal object for repeated validation</span></span>  
  
1.  <span data-ttu-id="4ccfc-107">Chiamare il metodo <xref:System.AppDomain.SetPrincipalPolicy%2A> sull'oggetto <xref:System.AppDomain> restituito dalla proprietà statica <xref:System.AppDomain.CurrentDomain%2A?displayProperty=nameWithType>, passando il metodo a un valore di enumerazione <xref:System.Security.Principal.PrincipalPolicy> che indica quale dovrebbero essere i nuovi criteri.</span><span class="sxs-lookup"><span data-stu-id="4ccfc-107">Call the <xref:System.AppDomain.SetPrincipalPolicy%2A> method on the <xref:System.AppDomain> object that is returned by the static <xref:System.AppDomain.CurrentDomain%2A?displayProperty=nameWithType> property, passing the method a <xref:System.Security.Principal.PrincipalPolicy> enumeration value that indicates what the new policy should be.</span></span> <span data-ttu-id="4ccfc-108">I valori supportati sono <xref:System.Security.Principal.PrincipalPolicy.NoPrincipal>, <xref:System.Security.Principal.PrincipalPolicy.UnauthenticatedPrincipal> e <xref:System.Security.Principal.PrincipalPolicy.WindowsPrincipal>.</span><span class="sxs-lookup"><span data-stu-id="4ccfc-108">Supported values are <xref:System.Security.Principal.PrincipalPolicy.NoPrincipal>, <xref:System.Security.Principal.PrincipalPolicy.UnauthenticatedPrincipal>, and <xref:System.Security.Principal.PrincipalPolicy.WindowsPrincipal>.</span></span> <span data-ttu-id="4ccfc-109">Il codice seguente illustra questa chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="4ccfc-109">The following code demonstrates this method call.</span></span>  
  
    ```csharp  
    AppDomain.CurrentDomain.SetPrincipalPolicy(  
        PrincipalPolicy.WindowsPrincipal);  
    ```  
  
    ```vb  
    AppDomain.CurrentDomain.SetPrincipalPolicy( _  
        PrincipalPolicy.WindowsPrincipal)  
    ```  
  
2.  <span data-ttu-id="4ccfc-110">Con i criteri impostati usare la proprietà statica <xref:System.Threading.Thread.CurrentPrincipal%2A?displayProperty=nameWithType> per richiamare l'entità che incapsula l'utente Windows corrente.</span><span class="sxs-lookup"><span data-stu-id="4ccfc-110">With the policy set, use the static <xref:System.Threading.Thread.CurrentPrincipal%2A?displayProperty=nameWithType> property to retrieve the principal that encapsulates the current Windows user.</span></span> <span data-ttu-id="4ccfc-111">Poiché il tipo restituito della proprietà è <xref:System.Security.Principal.IPrincipal>, si deve eseguire il cast del risultato a un tipo <xref:System.Security.Principal.WindowsPrincipal>.</span><span class="sxs-lookup"><span data-stu-id="4ccfc-111">Because the property return type is <xref:System.Security.Principal.IPrincipal>, you must cast the result to a <xref:System.Security.Principal.WindowsPrincipal> type.</span></span> <span data-ttu-id="4ccfc-112">Il codice seguente inizializza un nuovo oggetto <xref:System.Security.Principal.WindowsPrincipal> al valore dell'entità associata con il thread corrente.</span><span class="sxs-lookup"><span data-stu-id="4ccfc-112">The following code initializes a new <xref:System.Security.Principal.WindowsPrincipal> object to the value of the principal associated with the current thread.</span></span>  
  
    ```csharp  
    WindowsPrincipal MyPrincipal =   
        (WindowsPrincipal) Thread.CurrentPrincipal;  
    ```  
  
    ```vb  
    Dim MyPrincipal As WindowsPrincipal = _  
        CType(Thread.CurrentPrincipal, WindowsPrincipal)   
    ```  
  
3.  <span data-ttu-id="4ccfc-113">Quando l'oggetto Principal è stato creato, è possibile usare uno dei diversi metodi per convalidarlo.</span><span class="sxs-lookup"><span data-stu-id="4ccfc-113">When the principal object has been created, you can use one of several methods to validate it.</span></span>  
  
### <a name="to-create-a-windowsprincipal-object-for-a-single-validation"></a><span data-ttu-id="4ccfc-114">Per creare un oggetto WindowsPrincipal per una singola convalida</span><span class="sxs-lookup"><span data-stu-id="4ccfc-114">To create a WindowsPrincipal object for a single validation</span></span>  
  
1.  <span data-ttu-id="4ccfc-115">Inizializzare un nuovo oggetto <xref:System.Security.Principal.WindowsIdentity> chiamando il metodo statico <xref:System.Security.Principal.WindowsIdentity.GetCurrent%2A?displayProperty=nameWithType>, che sottopone a query l'account Windows corrente e inserisce le informazioni relative all'account in un oggetto Identity appena creato.</span><span class="sxs-lookup"><span data-stu-id="4ccfc-115">Initialize a new <xref:System.Security.Principal.WindowsIdentity> object by calling the static <xref:System.Security.Principal.WindowsIdentity.GetCurrent%2A?displayProperty=nameWithType> method, which queries the current Windows account and places information about that account into the newly created identity object.</span></span> <span data-ttu-id="4ccfc-116">Il codice seguente crea un nuovo oggetto <xref:System.Security.Principal.WindowsIdentity> e lo inizializza per l'utente autenticato corrente.</span><span class="sxs-lookup"><span data-stu-id="4ccfc-116">The following code creates a new <xref:System.Security.Principal.WindowsIdentity> object and initializes it to the current authenticated user.</span></span>  
  
    ```csharp  
    WindowsIdentity MyIdentity = WindowsIdentity.GetCurrent();  
    ```  
  
    ```vb  
    Dim MyIdentity As WindowsIdentity = WindowsIdentity.GetCurrent()  
    ```  
  
2.  <span data-ttu-id="4ccfc-117">Creare un nuovo oggetto <xref:System.Security.Principal.WindowsPrincipal> e passargli il valore dell'oggetto <xref:System.Security.Principal.WindowsIdentity> creato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="4ccfc-117">Create a new <xref:System.Security.Principal.WindowsPrincipal> object and pass it the value of the <xref:System.Security.Principal.WindowsIdentity> object created in the preceding step.</span></span>  
  
    ```csharp  
    WindowsPrincipal MyPrincipal = new WindowsPrincipal(MyIdentity);  
    ```  
  
    ```vb  
    Dim MyPrincipal As New WindowsPrincipal(MyIdentity)  
    ```  
  
3.  <span data-ttu-id="4ccfc-118">Quando l'oggetto Principal è stato creato, è possibile usare uno dei diversi metodi per convalidarlo.</span><span class="sxs-lookup"><span data-stu-id="4ccfc-118">When the principal object has been created, you can use one of several methods to validate it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ccfc-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ccfc-119">See also</span></span>

- [<span data-ttu-id="4ccfc-120">Oggetti Principal e Identity</span><span class="sxs-lookup"><span data-stu-id="4ccfc-120">Principal and Identity Objects</span></span>](../../../docs/standard/security/principal-and-identity-objects.md)
