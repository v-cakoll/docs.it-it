---
title: Specifica di un set di caratteri
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- platform invoke, attribute fields
- attribute fields in platform invoke, CharSet
- CharSet field
ms.assetid: a8347eb1-295f-46b9-8a78-63331f9ecc50
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 798fcacab5bd74dbd6569a68a3b598c0bb63a0a7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59087742"
---
# <a name="specifying-a-character-set"></a><span data-ttu-id="22469-102">Specifica di un set di caratteri</span><span class="sxs-lookup"><span data-stu-id="22469-102">Specifying a Character Set</span></span>
<span data-ttu-id="22469-103">Il campo <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> controlla il marshalling delle stringhe e determina in che modo la funzionalità platform invoke trova i nomi di funzione in una DLL.</span><span class="sxs-lookup"><span data-stu-id="22469-103">The <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> field controls string marshaling and determines how platform invoke finds function names in a DLL.</span></span> <span data-ttu-id="22469-104">Questo argomento descrive entrambi i comportamenti.</span><span class="sxs-lookup"><span data-stu-id="22469-104">This topic describes both behaviors.</span></span>  
  
 <span data-ttu-id="22469-105">Alcune API esportano due versioni delle funzioni che accettano argomenti stringa: narrow (ANSI) e wide (Unicode).</span><span class="sxs-lookup"><span data-stu-id="22469-105">Some APIs export two versions of functions that take string arguments: narrow (ANSI) and wide (Unicode).</span></span> <span data-ttu-id="22469-106">L'API Windows, ad esempio, include i seguenti nomi di punto di ingresso per la funzione **MessageBox**:</span><span class="sxs-lookup"><span data-stu-id="22469-106">The Windows API, for instance, includes the following entry-point names for the **MessageBox** function:</span></span>  
  
-   **<span data-ttu-id="22469-107">MessageBoxA</span><span class="sxs-lookup"><span data-stu-id="22469-107">MessageBoxA</span></span>**  
  
     <span data-ttu-id="22469-108">Fornisce la formattazione ANSI dei caratteri a 1 byte, con l'aggiunta di "A" al nome del punto di ingresso per poterla distinguere.</span><span class="sxs-lookup"><span data-stu-id="22469-108">Provides 1-byte character ANSI formatting, distinguished by an "A" appended to the entry-point name.</span></span> <span data-ttu-id="22469-109">Le chiamate a **MessageBoxA** eseguono sempre il marshalling delle stringhe in formato ANSI.</span><span class="sxs-lookup"><span data-stu-id="22469-109">Calls to **MessageBoxA** always marshal strings in ANSI format.</span></span>  
  
-   **<span data-ttu-id="22469-110">MessageBoxW</span><span class="sxs-lookup"><span data-stu-id="22469-110">MessageBoxW</span></span>**  
  
     <span data-ttu-id="22469-111">Fornisce la formattazione Unicode dei caratteri a 2 byte, con l'aggiunta di "W" al nome del punto di ingresso per poterla distinguere.</span><span class="sxs-lookup"><span data-stu-id="22469-111">Provides 2-byte character Unicode formatting, distinguished by a "W" appended to the entry-point name.</span></span> <span data-ttu-id="22469-112">Le chiamate a **MessageBoxW** eseguono sempre il marshalling delle stringhe in formato Unicode.</span><span class="sxs-lookup"><span data-stu-id="22469-112">Calls to **MessageBoxW** always marshal strings in Unicode format.</span></span>  
  
## <a name="string-marshaling-and-name-matching"></a><span data-ttu-id="22469-113">Marshalling delle stringhe e corrispondenza dei nomi</span><span class="sxs-lookup"><span data-stu-id="22469-113">String Marshaling and Name Matching</span></span>  
 <span data-ttu-id="22469-114">Il campo `CharSet` accetta i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="22469-114">The `CharSet` field accepts the following values:</span></span>  
  
 <xref:System.Runtime.InteropServices.CharSet.Ansi> <span data-ttu-id="22469-115">(valore predefinito)</span><span class="sxs-lookup"><span data-stu-id="22469-115">(default value)</span></span>  
  
-   <span data-ttu-id="22469-116">Marshalling delle stringhe</span><span class="sxs-lookup"><span data-stu-id="22469-116">String marshaling</span></span>  
  
     <span data-ttu-id="22469-117">La funzionalità platform invoke esegue il marshalling delle stringhe dal formato gestito (Unicode) al formato ANSI.</span><span class="sxs-lookup"><span data-stu-id="22469-117">Platform invoke marshals strings from their managed format (Unicode) to ANSI format.</span></span>  
  
-   <span data-ttu-id="22469-118">Corrispondenza dei nomi</span><span class="sxs-lookup"><span data-stu-id="22469-118">Name matching</span></span>  
  
     <span data-ttu-id="22469-119">Quando il campo <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling?displayProperty=nameWithType> è `true`, come per impostazione predefinita in [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], platform invoke cerca solo il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="22469-119">When the <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling?displayProperty=nameWithType> field is `true`, as it is by default in [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], platform invoke searches only for the name you specify.</span></span> <span data-ttu-id="22469-120">Ad esempio, se si specifica **MessageBox**, platform invoke cerca **MessageBox** e ha esito negativo quando non riesce a individuare la stringa con la stessa identica ortografia.</span><span class="sxs-lookup"><span data-stu-id="22469-120">For example, if you specify **MessageBox**, platform invoke searches for **MessageBox** and fails when it cannot locate the exact spelling.</span></span>  
  
     <span data-ttu-id="22469-121">Quando il campo `ExactSpelling` è `false`, come avviene per impostazione predefinita in C++ e C#, platform invoke cerca prima di tutto l'alias non modificato (**MessageBox**), poi il nome modificato (**MessageBoxA**) se non viene trovato l'alias non modificato.</span><span class="sxs-lookup"><span data-stu-id="22469-121">When the `ExactSpelling` field is `false`, as it is by default in C++ and C#, platform invoke searches for the unmangled alias first (**MessageBox**), then the mangled name (**MessageBoxA**) if the unmangled alias is not found.</span></span> <span data-ttu-id="22469-122">Si noti che il comportamento di corrispondenza dei nomi ANSI differisce dal comportamento di corrispondenza dei nomi Unicode.</span><span class="sxs-lookup"><span data-stu-id="22469-122">Notice that ANSI name-matching behavior differs from Unicode name-matching behavior.</span></span>  
  
 <xref:System.Runtime.InteropServices.CharSet.Unicode>  
  
-   <span data-ttu-id="22469-123">Marshalling delle stringhe</span><span class="sxs-lookup"><span data-stu-id="22469-123">String marshaling</span></span>  
  
     <span data-ttu-id="22469-124">La funzionalità platform invoke copia le stringhe dal formato gestito (Unicode) al formato Unicode.</span><span class="sxs-lookup"><span data-stu-id="22469-124">Platform invoke copies strings from their managed format (Unicode) to Unicode format.</span></span>  
  
-   <span data-ttu-id="22469-125">Corrispondenza dei nomi</span><span class="sxs-lookup"><span data-stu-id="22469-125">Name matching</span></span>  
  
     <span data-ttu-id="22469-126">Quando il campo `ExactSpelling` è `true`, come per impostazione predefinita in [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], platform invoke cerca solo il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="22469-126">When the `ExactSpelling` field is `true`, as it is by default in [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], platform invoke searches only for the name you specify.</span></span> <span data-ttu-id="22469-127">Ad esempio, se si specifica **MessageBox**, platform invoke cerca **MessageBox** e ha esito negativo se non riesce a individuare la stringa con la stessa identica ortografia.</span><span class="sxs-lookup"><span data-stu-id="22469-127">For example, if you specify **MessageBox**, platform invoke searches for **MessageBox** and fails if it cannot locate the exact spelling.</span></span>  
  
     <span data-ttu-id="22469-128">Quando il campo `ExactSpelling` è `false`, come avviene per impostazione predefinita in C++ e C#, platform invoke cerca prima di tutto il nome modificato (**MessageBoxW**), poi l'alias non modificato (**MessageBox**) se non viene trovato il nome modificato.</span><span class="sxs-lookup"><span data-stu-id="22469-128">When the `ExactSpelling` field is `false`, as it is by default in C++ and C#, platform invoke searches for the mangled name first (**MessageBoxW**), then the unmangled alias (**MessageBox**) if the mangled name is not found.</span></span> <span data-ttu-id="22469-129">Si noti che il comportamento di corrispondenza dei nomi Unicode differisce dal comportamento di corrispondenza dei nomi ANSI.</span><span class="sxs-lookup"><span data-stu-id="22469-129">Notice that Unicode name-matching behavior differs from ANSI name-matching behavior.</span></span>  
  
 <xref:System.Runtime.InteropServices.CharSet.Auto>  
  
-   <span data-ttu-id="22469-130">La funzionalità platform invoke sceglie tra i formati ANSI e Unicode in fase di esecuzione, in base alla piattaforma di destinazione.</span><span class="sxs-lookup"><span data-stu-id="22469-130">Platform invoke chooses between ANSI and Unicode formats at run time, based on the target platform.</span></span>  
  
## <a name="specifying-a-character-set-in-visual-basic"></a><span data-ttu-id="22469-131">Specifica un set di caratteri in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="22469-131">Specifying a Character Set in Visual Basic</span></span>  
 <span data-ttu-id="22469-132">L'esempio seguente dichiara la funzione **MessageBox** tre volte, ogni volta con un diverso comportamento per il set di caratteri.</span><span class="sxs-lookup"><span data-stu-id="22469-132">The following example declares the **MessageBox** function three times, each time with different character-set behavior.</span></span> <span data-ttu-id="22469-133">È possibile specificare il comportamento per il set di caratteri in Visual Basic aggiungendo la parola chiave **Ansi**, **Unicode** o **Auto** nell'istruzione di dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="22469-133">You can specify character-set behavior in Visual Basic by adding the **Ansi**, **Unicode**, or **Auto** keyword to the declaration statement.</span></span>  
  
 <span data-ttu-id="22469-134">Se si omette la parola chiave per il set di caratteri, come avviene nella prima istruzione di dichiarazione, il campo <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> usa il set di caratteri ANSI per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="22469-134">If you omit the character-set keyword, as is done in the first declaration statement, the <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> field defaults to the ANSI character set.</span></span> <span data-ttu-id="22469-135">La seconda e la terza istruzione nell'esempio specificano in modo esplicito un set di caratteri con una parola chiave.</span><span class="sxs-lookup"><span data-stu-id="22469-135">The second and third statements in the example explicitly specify a character set with a keyword.</span></span>  
  
```vb
Imports System

Friend Class WindowsAPI
    Friend Shared Declare Function MessageBoxA Lib "user32.dll" (
        ByVal hWnd As IntPtr,
        ByVal lpText As String,
        ByVal lpCaption As String,
        ByVal uType As UInteger) As Integer

    Friend Shared Declare Unicode Function MessageBoxW Lib "user32.dll" (
        ByVal hWnd As IntPtr,
        ByVal lpText As String,
        ByVal lpCaption As String,
        ByVal uType As UInteger) As Integer

    Friend Shared Declare Auto Function MessageBox Lib "user32.dll" (
        ByVal hWnd As IntPtr,
        ByVal lpText As String,
        ByVal lpCaption As String,
        ByVal uType As UInteger) As Integer
End Class
```
  
## <a name="specifying-a-character-set-in-c-and-c"></a><span data-ttu-id="22469-136">Specifica di un set di caratteri in C# e C++</span><span class="sxs-lookup"><span data-stu-id="22469-136">Specifying a Character Set in C# and C++</span></span>  
 <span data-ttu-id="22469-137">Il campo <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> identifica il set di caratteri sottostante come ANSI o Unicode.</span><span class="sxs-lookup"><span data-stu-id="22469-137">The <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> field identifies the underlying character set as ANSI or Unicode.</span></span> <span data-ttu-id="22469-138">Il set di caratteri controlla la modalità di marshalling degli argomenti stringa per un metodo.</span><span class="sxs-lookup"><span data-stu-id="22469-138">The character set controls how string arguments to a method should be marshaled.</span></span> <span data-ttu-id="22469-139">Usare una delle forme seguenti per indicare il set di caratteri:</span><span class="sxs-lookup"><span data-stu-id="22469-139">Use one of the following forms to indicate the character set:</span></span>  
  
```csharp
[DllImport("DllName", CharSet = CharSet.Ansi)]
[DllImport("DllName", CharSet = CharSet.Unicode)]
[DllImport("DllName", CharSet = CharSet.Auto)]
```
  
```cpp
[DllImport("DllName", CharSet = CharSet::Ansi)]
[DllImport("DllName", CharSet = CharSet::Unicode)]
[DllImport("DllName", CharSet = CharSet::Auto)]
```
  
 <span data-ttu-id="22469-140">L'esempio seguente mostra tre definizioni gestite della funzione **MessageBox** attribuite a un set di caratteri specifico.</span><span class="sxs-lookup"><span data-stu-id="22469-140">The following example shows three managed definitions of the **MessageBox** function attributed to specify a character set.</span></span> <span data-ttu-id="22469-141">Nella prima definizione, con l'omissione, il campo `CharSet` usa per impostazione predefinita il set di caratteri ANSI.</span><span class="sxs-lookup"><span data-stu-id="22469-141">In the first definition, by its omission, the `CharSet` field defaults to the ANSI character set.</span></span>  
  
```csharp  
using System;
using System.Runtime.InteropServices;

internal static class WindowsAPI
{
    [DllImport("user32.dll")]
    internal static extern int MessageBoxA(
        IntPtr hWnd, string lpText, string lpCaption, uint uType);

    [DllImport("user32.dll", CharSet = CharSet.Unicode)]
    internal static extern int MessageBoxW(
        IntPtr hWnd, string lpText, string lpCaption, uint uType);

    [DllImport("user32.dll", CharSet = CharSet.Auto)]
    internal static extern int MessageBox(
        IntPtr hWnd, string lpText, string lpCaption, uint uType);
}
```  
  
```cpp
typedef void* HWND;

// Can use MessageBox or MessageBoxA.
[DllImport("user32")]
extern "C" int MessageBox(
    HWND hWnd, String* lpText, String* lpCaption, unsigned int uType);

// Can use MessageBox or MessageBoxW.
[DllImport("user32", CharSet = CharSet::Unicode)]
extern "C" int MessageBoxW(
    HWND hWnd, String* lpText, String* lpCaption, unsigned int uType);

// Must use MessageBox.
[DllImport("user32", CharSet = CharSet::Auto)]
extern "C" int MessageBox(
    HWND hWnd, String* lpText, String* lpCaption, unsigned int uType);
```
  
## <a name="see-also"></a><span data-ttu-id="22469-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="22469-142">See also</span></span>

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [<span data-ttu-id="22469-143">Creazione di prototipi nel codice gestito</span><span class="sxs-lookup"><span data-stu-id="22469-143">Creating Prototypes in Managed Code</span></span>](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)
- [<span data-ttu-id="22469-144">Esempi di platform invoke</span><span class="sxs-lookup"><span data-stu-id="22469-144">Platform Invoke Examples</span></span>](../../../docs/framework/interop/platform-invoke-examples.md)
- [<span data-ttu-id="22469-145">Marshalling dei dati con platform invoke</span><span class="sxs-lookup"><span data-stu-id="22469-145">Marshaling Data with Platform Invoke</span></span>](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)
