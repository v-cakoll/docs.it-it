---
title: 'Mitigazione: MemberDescriptor.Equals'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cf3735f0-0dd4-4bef-b4b0-575264e10f39
caps.latest.revision: 7
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 4989d3c2611b500063158955f102931902e1ab32
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-memberdescriptorequals"></a><span data-ttu-id="ef931-102">Mitigazione: MemberDescriptor.Equals</span><span class="sxs-lookup"><span data-stu-id="ef931-102">Mitigation: MemberDescriptor.Equals</span></span>
<span data-ttu-id="ef931-103">A partire dalle applicazioni destinate a [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], l'implementazione del metodo <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> è stata modificata.</span><span class="sxs-lookup"><span data-stu-id="ef931-103">Starting with apps that target the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], the implementation of the <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> method has changed.</span></span> <span data-ttu-id="ef931-104">Poiché i metodi `System.ComponentModel.EventDescriptor.Equals` e `System.ComponentModel.PropertyDescriptor.Equals` ereditano l'implementazione della classe base, la modifica interesserà anche questi metodi.</span><span class="sxs-lookup"><span data-stu-id="ef931-104">Because the `System.ComponentModel.EventDescriptor.Equals` and  `System.ComponentModel.PropertyDescriptor.Equals` methods inherit the base class implementation, the change also affects these methods.</span></span>  
  
 <span data-ttu-id="ef931-105">Nelle app destinate alle versioni di .NET Framework precedenti a [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], una parte del test del metodo <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> per la verifica dell'uguaglianza confronta in modo non corretto la proprietà <xref:System.ComponentModel.MemberDescriptor.Category%2A?displayProperty=fullName> di un oggetto con la proprietà <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=fullName> dell'altro.</span><span class="sxs-lookup"><span data-stu-id="ef931-105">In apps that target versions of the .NET Framework prior to [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], a portion of the <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> method's test for equality  incorrectly compared the <xref:System.ComponentModel.MemberDescriptor.Category%2A?displayProperty=fullName> property of one object with the <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=fullName> property of the other.</span></span> <span data-ttu-id="ef931-106">A partire dalle app destinate a [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], il metodo <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> confronta la proprietà <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=fullName> dei due oggetti.</span><span class="sxs-lookup"><span data-stu-id="ef931-106">Starting with apps that target the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], the <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> method compares the <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=fullName> property of the two objects.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="ef931-107">Impatto</span><span class="sxs-lookup"><span data-stu-id="ef931-107">Impact</span></span>  
 <span data-ttu-id="ef931-108">Questa modifica implementa correttamente il test dell'uguaglianza per gli oggetti <xref:System.ComponentModel.MemberDescriptor?displayProperty=fullName> e deve avere un impatto minimo.</span><span class="sxs-lookup"><span data-stu-id="ef931-108">This change correctly implements the test for equality for <xref:System.ComponentModel.MemberDescriptor?displayProperty=fullName> objects and should have minimal impact.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="ef931-109">Attenuazione</span><span class="sxs-lookup"><span data-stu-id="ef931-109">Mitigation</span></span>  
 <span data-ttu-id="ef931-110">Sono disponibili due soluzioni alternative se le app sono destinate a [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] o a una versione successiva di .NET Framework. La scelta dipende dal metodo <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> che a volte restituisce `false` quando i descrittori di membro sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="ef931-110">Two workarounds are available if your app targets the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] or a later version of the .NET Framework and it depends on the  <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> method sometimes returning `false` when member descriptors are equivalent:</span></span>  
  
-   <span data-ttu-id="ef931-111">È possibile rifiutare esplicitamente questa modifica senza modificare il codice sorgente aggiungendo il codice seguente alla sezione [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del file app.config:</span><span class="sxs-lookup"><span data-stu-id="ef931-111">You can opt out of this change without modifying your source code by adding the following to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your app.config file:</span></span>  
  
    ```xml  
    <runtime>  
        <AppContextSwitchOverrides value = "Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=true" />  
     </runtime>  
    ```  
  
-   <span data-ttu-id="ef931-112">È possibile modificare il codice sorgente per ripristinare il comportamento precedente confrontando manualmente le proprietà <xref:System.ComponentModel.MemberDescriptor.Category%2A?displayProperty=fullName> e <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=fullName> dopo la chiamata al metodo <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName>, come nel seguente frammento di codice.</span><span class="sxs-lookup"><span data-stu-id="ef931-112">You can modify your source code to restore the previous behavior by manually comparing the  <xref:System.ComponentModel.MemberDescriptor.Category%2A?displayProperty=fullName> and <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=fullName> properties after calling the <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> method, as the following code fragment does.</span></span>  
  
    ```csharp  
    if (memberDescriptor1.Equals(memberDescriptor2) &   
        memberDescriptor1.Description.Equals(memberDescriptor2.Category)) {  
          // Code to execute if true.  
    }  
    else {  
          // Code to execute if false.     
    }  
    ```  
  
    ```  
    If memberDescriptor1.Equals(memberDescriptor2) And   
        memberDescriptor1.Description.Equals(memberDescriptor2.Category)  
          // Code to execute if True.  
    Else  
          // Code to execute if False.     
    End If  
    ```  
  
 <span data-ttu-id="ef931-113">Per le applicazioni destinate a [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] e versioni precedenti, è possibile abilitare questa modifica aggiungendo il valore seguente al file app.config:</span><span class="sxs-lookup"><span data-stu-id="ef931-113">For apps that target the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] and earlier versions, you can enable this change by adding the following value to your app.config file:</span></span>  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=true />  
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ef931-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ef931-114">See Also</span></span>  
 <span data-ttu-id="ef931-115">[Modifiche di reindirizzamento](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-2.md) </span><span class="sxs-lookup"><span data-stu-id="ef931-115">[Retargeting Changes](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-2.md) </span></span>  
 [<span data-ttu-id="ef931-116">Compatibilità delle applicazioni nella versione 4.6.2</span><span class="sxs-lookup"><span data-stu-id="ef931-116">Application Compatibility in 4.6.2</span></span>](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-2.md)

