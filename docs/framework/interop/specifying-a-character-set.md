---
title: Specifica di un set di caratteri
description: Informazioni su come specificare un set di caratteri che usa la codifica Narrow (ANSI) o Wide (Unicode). In alternativa, è possibile specificare la selezione automatica del runtime.
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
ms.openlocfilehash: 789753742d8714e481f038e323407cbab0499f6c
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309794"
---
# <a name="specify-a-character-set"></a><span data-ttu-id="7ace6-104">Specificare un set di caratteri</span><span class="sxs-lookup"><span data-stu-id="7ace6-104">Specify a character set</span></span>

<span data-ttu-id="7ace6-105">Il campo <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> controlla il marshalling delle stringhe e determina in che modo la funzionalità platform invoke trova i nomi di funzione in una DLL.</span><span class="sxs-lookup"><span data-stu-id="7ace6-105">The <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> field controls string marshaling and determines how platform invoke finds function names in a DLL.</span></span> <span data-ttu-id="7ace6-106">Questo argomento descrive entrambi i comportamenti.</span><span class="sxs-lookup"><span data-stu-id="7ace6-106">This topic describes both behaviors.</span></span>  
  
 <span data-ttu-id="7ace6-107">Alcune API esportano due versioni delle funzioni che accettano argomenti stringa: narrow (ANSI) e wide (Unicode).</span><span class="sxs-lookup"><span data-stu-id="7ace6-107">Some APIs export two versions of functions that take string arguments: narrow (ANSI) and wide (Unicode).</span></span> <span data-ttu-id="7ace6-108">L'API Windows, ad esempio, include i seguenti nomi di punto di ingresso per la funzione **MessageBox**:</span><span class="sxs-lookup"><span data-stu-id="7ace6-108">The Windows API, for instance, includes the following entry-point names for the **MessageBox** function:</span></span>  
  
- <span data-ttu-id="7ace6-109">**MessageBoxA**</span><span class="sxs-lookup"><span data-stu-id="7ace6-109">**MessageBoxA**</span></span>  
  
     <span data-ttu-id="7ace6-110">Fornisce la formattazione ANSI dei caratteri a 1 byte, con l'aggiunta di "A" al nome del punto di ingresso per poterla distinguere.</span><span class="sxs-lookup"><span data-stu-id="7ace6-110">Provides 1-byte character ANSI formatting, distinguished by an "A" appended to the entry-point name.</span></span> <span data-ttu-id="7ace6-111">Le chiamate a **MessageBoxA** eseguono sempre il marshalling delle stringhe in formato ANSI.</span><span class="sxs-lookup"><span data-stu-id="7ace6-111">Calls to **MessageBoxA** always marshal strings in ANSI format.</span></span>  
  
- <span data-ttu-id="7ace6-112">**MessageBoxW**</span><span class="sxs-lookup"><span data-stu-id="7ace6-112">**MessageBoxW**</span></span>  
  
     <span data-ttu-id="7ace6-113">Fornisce la formattazione Unicode dei caratteri a 2 byte, con l'aggiunta di "W" al nome del punto di ingresso per poterla distinguere.</span><span class="sxs-lookup"><span data-stu-id="7ace6-113">Provides 2-byte character Unicode formatting, distinguished by a "W" appended to the entry-point name.</span></span> <span data-ttu-id="7ace6-114">Le chiamate a **MessageBoxW** eseguono sempre il marshalling delle stringhe in formato Unicode.</span><span class="sxs-lookup"><span data-stu-id="7ace6-114">Calls to **MessageBoxW** always marshal strings in Unicode format.</span></span>  
  
## <a name="string-marshaling-and-name-matching"></a><span data-ttu-id="7ace6-115">Marshalling delle stringhe e corrispondenza dei nomi</span><span class="sxs-lookup"><span data-stu-id="7ace6-115">String Marshaling and Name Matching</span></span>  
 <span data-ttu-id="7ace6-116">Il campo `CharSet` accetta i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="7ace6-116">The `CharSet` field accepts the following values:</span></span>  
  
 <span data-ttu-id="7ace6-117"><xref:System.Runtime.InteropServices.CharSet.Ansi> (valore predefinito)</span><span class="sxs-lookup"><span data-stu-id="7ace6-117"><xref:System.Runtime.InteropServices.CharSet.Ansi> (default value)</span></span>  
  
- <span data-ttu-id="7ace6-118">Marshalling delle stringhe</span><span class="sxs-lookup"><span data-stu-id="7ace6-118">String marshaling</span></span>  
  
     <span data-ttu-id="7ace6-119">La funzionalità platform invoke esegue il marshalling delle stringhe dal formato gestito (Unicode) al formato ANSI.</span><span class="sxs-lookup"><span data-stu-id="7ace6-119">Platform invoke marshals strings from their managed format (Unicode) to ANSI format.</span></span>  
  
- <span data-ttu-id="7ace6-120">Corrispondenza dei nomi</span><span class="sxs-lookup"><span data-stu-id="7ace6-120">Name matching</span></span>  
  
     <span data-ttu-id="7ace6-121">Quando il campo <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling?displayProperty=nameWithType> è `true`, come per impostazione predefinita in Visual Basic, platform invoke cerca solo il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="7ace6-121">When the <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling?displayProperty=nameWithType> field is `true`, as it is by default in Visual Basic, platform invoke searches only for the name you specify.</span></span> <span data-ttu-id="7ace6-122">Ad esempio, se si specifica **MessageBox**, platform invoke cerca **MessageBox** e ha esito negativo quando non riesce a individuare la stringa con la stessa identica ortografia.</span><span class="sxs-lookup"><span data-stu-id="7ace6-122">For example, if you specify **MessageBox**, platform invoke searches for **MessageBox** and fails when it cannot locate the exact spelling.</span></span>  
  
     <span data-ttu-id="7ace6-123">Quando il campo `ExactSpelling` è `false`, come avviene per impostazione predefinita in C++ e C#, platform invoke cerca prima di tutto l'alias non modificato (**MessageBox**), poi il nome modificato (**MessageBoxA**) se non viene trovato l'alias non modificato.</span><span class="sxs-lookup"><span data-stu-id="7ace6-123">When the `ExactSpelling` field is `false`, as it is by default in C++ and C#, platform invoke searches for the unmangled alias first (**MessageBox**), then the mangled name (**MessageBoxA**) if the unmangled alias is not found.</span></span> <span data-ttu-id="7ace6-124">Si noti che il comportamento di corrispondenza dei nomi ANSI differisce dal comportamento di corrispondenza dei nomi Unicode.</span><span class="sxs-lookup"><span data-stu-id="7ace6-124">Notice that ANSI name-matching behavior differs from Unicode name-matching behavior.</span></span>  
  
 <xref:System.Runtime.InteropServices.CharSet.Unicode>  
  
- <span data-ttu-id="7ace6-125">Marshalling delle stringhe</span><span class="sxs-lookup"><span data-stu-id="7ace6-125">String marshaling</span></span>  
  
     <span data-ttu-id="7ace6-126">La funzionalità platform invoke copia le stringhe dal formato gestito (Unicode) al formato Unicode.</span><span class="sxs-lookup"><span data-stu-id="7ace6-126">Platform invoke copies strings from their managed format (Unicode) to Unicode format.</span></span>  
  
- <span data-ttu-id="7ace6-127">Corrispondenza dei nomi</span><span class="sxs-lookup"><span data-stu-id="7ace6-127">Name matching</span></span>  
  
     <span data-ttu-id="7ace6-128">Quando il campo `ExactSpelling` è `true`, come per impostazione predefinita in Visual Basic, platform invoke cerca solo il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="7ace6-128">When the `ExactSpelling` field is `true`, as it is by default in Visual Basic, platform invoke searches only for the name you specify.</span></span> <span data-ttu-id="7ace6-129">Ad esempio, se si specifica **MessageBox**, platform invoke cerca **MessageBox** e ha esito negativo se non riesce a individuare la stringa con la stessa identica ortografia.</span><span class="sxs-lookup"><span data-stu-id="7ace6-129">For example, if you specify **MessageBox**, platform invoke searches for **MessageBox** and fails if it cannot locate the exact spelling.</span></span>  
  
     <span data-ttu-id="7ace6-130">Quando il campo `ExactSpelling` è `false`, come avviene per impostazione predefinita in C++ e C#, platform invoke cerca prima di tutto il nome modificato (**MessageBoxW**), poi l'alias non modificato (**MessageBox**) se non viene trovato il nome modificato.</span><span class="sxs-lookup"><span data-stu-id="7ace6-130">When the `ExactSpelling` field is `false`, as it is by default in C++ and C#, platform invoke searches for the mangled name first (**MessageBoxW**), then the unmangled alias (**MessageBox**) if the mangled name is not found.</span></span> <span data-ttu-id="7ace6-131">Si noti che il comportamento di corrispondenza dei nomi Unicode differisce dal comportamento di corrispondenza dei nomi ANSI.</span><span class="sxs-lookup"><span data-stu-id="7ace6-131">Notice that Unicode name-matching behavior differs from ANSI name-matching behavior.</span></span>  
  
 <xref:System.Runtime.InteropServices.CharSet.Auto>  
  
- <span data-ttu-id="7ace6-132">La funzionalità platform invoke sceglie tra i formati ANSI e Unicode in fase di esecuzione, in base alla piattaforma di destinazione.</span><span class="sxs-lookup"><span data-stu-id="7ace6-132">Platform invoke chooses between ANSI and Unicode formats at run time, based on the target platform.</span></span>  
  
## <a name="specify-a-character-set-in-visual-basic"></a><span data-ttu-id="7ace6-133">Specificare un set di caratteri in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7ace6-133">Specify a character set in Visual Basic</span></span>

<span data-ttu-id="7ace6-134">È possibile specificare il comportamento del set di caratteri in Visual Basic aggiungendo `Ansi` la `Unicode` `Auto` parola chiave, o all'istruzione di dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="7ace6-134">You can specify character-set behavior in Visual Basic by adding the `Ansi`, `Unicode`, or `Auto` keyword to the declaration statement.</span></span> <span data-ttu-id="7ace6-135">Se si omette la parola chiave set di caratteri, <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> per impostazione predefinita il campo viene impostato sul set di caratteri ANSI.</span><span class="sxs-lookup"><span data-stu-id="7ace6-135">If you omit the character-set keyword, the <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> field defaults to the ANSI character set.</span></span>

<span data-ttu-id="7ace6-136">L'esempio seguente dichiara la funzione **MessageBox** tre volte, ogni volta con un diverso comportamento per il set di caratteri.</span><span class="sxs-lookup"><span data-stu-id="7ace6-136">The following example declares the **MessageBox** function three times, each time with different character-set behavior.</span></span> <span data-ttu-id="7ace6-137">La prima istruzione omette la parola chiave del set di caratteri, quindi il set di caratteri predefinito è ANSI.</span><span class="sxs-lookup"><span data-stu-id="7ace6-137">The first statement omits the character-set keyword, so the character set defaults to ANSI.</span></span> <span data-ttu-id="7ace6-138">La seconda e la terza istruzione specificano in modo esplicito un set di caratteri con una parola chiave.</span><span class="sxs-lookup"><span data-stu-id="7ace6-138">The second and third statements explicitly specify a character set with a keyword.</span></span>

```vb
Friend Class NativeMethods
    Friend Declare Function MessageBoxA Lib "user32.dll" (
        ByVal hWnd As IntPtr,
        ByVal lpText As String,
        ByVal lpCaption As String,
        ByVal uType As UInteger) As Integer

    Friend Declare Unicode Function MessageBoxW Lib "user32.dll" (
        ByVal hWnd As IntPtr,
        ByVal lpText As String,
        ByVal lpCaption As String,
        ByVal uType As UInteger) As Integer

    Friend Declare Auto Function MessageBox Lib "user32.dll" (
        ByVal hWnd As IntPtr,
        ByVal lpText As String,
        ByVal lpCaption As String,
        ByVal uType As UInteger) As Integer
End Class
```
  
## <a name="specify-a-character-set-in-c-and-c"></a><span data-ttu-id="7ace6-139">Specificare un set di caratteri in C# e C++</span><span class="sxs-lookup"><span data-stu-id="7ace6-139">Specify a character set in C# and C++</span></span>

<span data-ttu-id="7ace6-140">Il campo <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> identifica il set di caratteri sottostante come ANSI o Unicode.</span><span class="sxs-lookup"><span data-stu-id="7ace6-140">The <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> field identifies the underlying character set as ANSI or Unicode.</span></span> <span data-ttu-id="7ace6-141">Il set di caratteri controlla la modalità di marshalling degli argomenti stringa per un metodo.</span><span class="sxs-lookup"><span data-stu-id="7ace6-141">The character set controls how string arguments to a method should be marshaled.</span></span> <span data-ttu-id="7ace6-142">Usare una delle forme seguenti per indicare il set di caratteri:</span><span class="sxs-lookup"><span data-stu-id="7ace6-142">Use one of the following forms to indicate the character set:</span></span>  
  
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
  
 <span data-ttu-id="7ace6-143">L'esempio seguente mostra tre definizioni gestite della funzione **MessageBox** attribuite a un set di caratteri specifico.</span><span class="sxs-lookup"><span data-stu-id="7ace6-143">The following example shows three managed definitions of the **MessageBox** function attributed to specify a character set.</span></span> <span data-ttu-id="7ace6-144">Nella prima definizione, con l'omissione, il campo `CharSet` usa per impostazione predefinita il set di caratteri ANSI.</span><span class="sxs-lookup"><span data-stu-id="7ace6-144">In the first definition, by its omission, the `CharSet` field defaults to the ANSI character set.</span></span>  
  
```csharp  
using System;
using System.Runtime.InteropServices;

internal static class NativeMethods
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
  
## <a name="see-also"></a><span data-ttu-id="7ace6-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ace6-145">See also</span></span>

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [<span data-ttu-id="7ace6-146">Creazione di prototipi nel codice gestito</span><span class="sxs-lookup"><span data-stu-id="7ace6-146">Creating Prototypes in Managed Code</span></span>](creating-prototypes-in-managed-code.md)
- [<span data-ttu-id="7ace6-147">Esempi di platform invoke</span><span class="sxs-lookup"><span data-stu-id="7ace6-147">Platform Invoke Examples</span></span>](platform-invoke-examples.md)
- [<span data-ttu-id="7ace6-148">Marshalling dei dati con platform invoke</span><span class="sxs-lookup"><span data-stu-id="7ace6-148">Marshaling Data with Platform Invoke</span></span>](marshaling-data-with-platform-invoke.md)
