---
title: 'Mitigazione: CspParameters.ParentWindowHandle prevede un HWND'
ms.custom: 
ms.date: 04/07/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- retargeting changes
- .NET Framework 4.7 retargeting changes
- CspParameters.ParentWindowHandle
- CspParameters.ParentWindowHandle retargeting change
ms.assetid: 33264333-71d6-4d43-8827-9c98878cfea7
caps.latest.revision: 5
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1b65aaf7149ca29b2af3efdf44ee9489a04c73a2
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-cspparametersparentwindowhandle-expects-an-hwnd"></a><span data-ttu-id="e79e3-102">Mitigazione: CspParameters.ParentWindowHandle prevede un HWND</span><span class="sxs-lookup"><span data-stu-id="e79e3-102">Mitigation: CspParameters.ParentWindowHandle Expects an HWND</span></span>

<span data-ttu-id="e79e3-103">La proprietà <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle%2A>, introdotta in .NET Framework 2.0, consente a un'applicazione di registrare il valore di un handle di finestra padre in modo che qualsiasi interfaccia utente necessaria per accedere alla chiave (ad esempio, una finestra di dialogo di richiesta di PIN o di consenso) venga aperta come finestra figlio modale nella finestra specificata.</span><span class="sxs-lookup"><span data-stu-id="e79e3-103">The <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle%2A> property, introduced in the .NET Framework 2.0, allows an application to register a parent window handle value such that any UI required to access the key (such as a PIN prompt or a consent dialog) opens as a modal child to the specified window.</span></span> <span data-ttu-id="e79e3-104">A partire dalle applicazioni per .NET Framework 4.7, un handle di finestra (HWND) può essere assegnato a questa proprietà.</span><span class="sxs-lookup"><span data-stu-id="e79e3-104">Starting with applications that target the .NET Framework 4.7, a window handle (HWND) can be assigned to this property.</span></span>

<span data-ttu-id="e79e3-105">Nelle versioni di .NET Framework fino a .NET Framework 4.6.2, il valore assegnato alla proprietà <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle%2A> deve essere <xref:System.IntPtr> per indicare la posizione in cui risiede il valore HWND nella memoria.</span><span class="sxs-lookup"><span data-stu-id="e79e3-105">In versions of the .NET Framework through the .NET Framework 4.6.2, the value assigned to the <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle%2A> property was expected to be an <xref:System.IntPtr> that represents the location in memory where the HWND value resided.</span></span> <span data-ttu-id="e79e3-106">In Windows 7 e nelle versioni precedenti del sistema operativo Windows, impostare la proprietà su `form.Handle` non aveva alcun effetto, mentre in Windows 8 e nelle versioni successive il risultato è <xref:System.Security.Cryptography> con il messaggio "Parametro non corretto".</span><span class="sxs-lookup"><span data-stu-id="e79e3-106">On Windows 7 and earlier versions of the Windows operating system, setting the property to `form.Handle` had no effect, but on Windows 8 and later versions, it results in a <xref:System.Security.Cryptography> with the message, "The parameter is incorrect."</span></span>

<span data-ttu-id="e79e3-107">A partire dalle applicazioni destinate a .NET Framework 4.7, un'applicazione Windows Forms può impostare la proprietà <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle%2A> con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="e79e3-107">Starting with apps that target the .NET Framework 4.7, a Windows Forms application can set the <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle%2A> property with code like the following:</span></span>

```csharp
cspParameters.ParentWindowHandle = form.Handle;
``` 

## <a name="impact"></a><span data-ttu-id="e79e3-108">Impatto</span><span class="sxs-lookup"><span data-stu-id="e79e3-108">Impact</span></span>

<span data-ttu-id="e79e3-109">Le applicazioni destinate a .NET Framework 4.7 o versioni successive che desiderano registrare una relazione della finestra padre sono invitate a usare la forma semplificata:</span><span class="sxs-lookup"><span data-stu-id="e79e3-109">Applications targeting the .NET Framework 4.7 or later that wish to register a parent window relationship are encouraged to use the simplified form:</span></span>

```csharp
cspParameters.ParentWindowHandle = form.Handle;
``` 

## <a name="mitigation"></a><span data-ttu-id="e79e3-110">Attenuazione</span><span class="sxs-lookup"><span data-stu-id="e79e3-110">Mitigation</span></span>

<span data-ttu-id="e79e3-111">Gli sviluppatori che hanno identificato il valore corretto nell'indirizzo della posizione di memoria contenente il valore `form.Handle` possono rifiutare esplicitamente questa modifica nel comportamento impostando l'opzione <xref:System.AppContext> `Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle` su `true`:</span><span class="sxs-lookup"><span data-stu-id="e79e3-111">Developers who had identified that the correct value was the address of the memory location that held the `form.Handle` value can opt out of this change in behavior by setting the <xref:System.AppContext> switch `Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle` to `true`:</span></span>

- <span data-ttu-id="e79e3-112">Impostando a livello di codice le opzioni di compatibilità sull'istanza <xref:System.AppContext>.</span><span class="sxs-lookup"><span data-stu-id="e79e3-112">By programmatically setting compatibility switches on the <xref:System.AppContext> instance.</span></span>

- <span data-ttu-id="e79e3-113">Aggiungendo la riga seguente alla sezione `<runtime>` del file app.config:</span><span class="sxs-lookup"><span data-stu-id="e79e3-113">By adding the following line to the `<runtime>` section of the app.config file:</span></span>
   
   ```xml
   <runtime>
     <AppContextSwitchOverrides value="Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle=true"/>
   </runtime>
   ```

<span data-ttu-id="e79e3-114">Al contrario, gli utenti che optano per il nuovo comportamento per le applicazioni eseguite in .NET Framework 4.7 ma destinate a una versione precedente di .NET Framework possono impostare l'opzione <xref:System.AppContext> su `false`.</span><span class="sxs-lookup"><span data-stu-id="e79e3-114">Conversely, users who wish to opt in to the new behavior for applications that run under the .NET Framework 4.7 but target an earlier version of the .NET Framework versions can set the <xref:System.AppContext> switch to `false`.</span></span>
 
## <a name="see-also"></a><span data-ttu-id="e79e3-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e79e3-115">See also</span></span>

[<span data-ttu-id="e79e3-116">Retargeting Changes in the .NET Framework 4.7 (Reindirizzamento delle modifiche in .NET Framework 4.7)</span><span class="sxs-lookup"><span data-stu-id="e79e3-116">Retargeting Changes in the .NET Framework 4.7</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-7.md)

