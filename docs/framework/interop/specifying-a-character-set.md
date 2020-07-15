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
# <a name="specify-a-character-set"></a>Specificare un set di caratteri

Il campo <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> controlla il marshalling delle stringhe e determina in che modo la funzionalità platform invoke trova i nomi di funzione in una DLL. Questo argomento descrive entrambi i comportamenti.  
  
 Alcune API esportano due versioni delle funzioni che accettano argomenti stringa: narrow (ANSI) e wide (Unicode). L'API Windows, ad esempio, include i seguenti nomi di punto di ingresso per la funzione **MessageBox**:  
  
- **MessageBoxA**  
  
     Fornisce la formattazione ANSI dei caratteri a 1 byte, con l'aggiunta di "A" al nome del punto di ingresso per poterla distinguere. Le chiamate a **MessageBoxA** eseguono sempre il marshalling delle stringhe in formato ANSI.  
  
- **MessageBoxW**  
  
     Fornisce la formattazione Unicode dei caratteri a 2 byte, con l'aggiunta di "W" al nome del punto di ingresso per poterla distinguere. Le chiamate a **MessageBoxW** eseguono sempre il marshalling delle stringhe in formato Unicode.  
  
## <a name="string-marshaling-and-name-matching"></a>Marshalling delle stringhe e corrispondenza dei nomi  
 Il campo `CharSet` accetta i valori seguenti:  
  
 <xref:System.Runtime.InteropServices.CharSet.Ansi> (valore predefinito)  
  
- Marshalling delle stringhe  
  
     La funzionalità platform invoke esegue il marshalling delle stringhe dal formato gestito (Unicode) al formato ANSI.  
  
- Corrispondenza dei nomi  
  
     Quando il campo <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling?displayProperty=nameWithType> è `true`, come per impostazione predefinita in Visual Basic, platform invoke cerca solo il nome specificato. Ad esempio, se si specifica **MessageBox**, platform invoke cerca **MessageBox** e ha esito negativo quando non riesce a individuare la stringa con la stessa identica ortografia.  
  
     Quando il campo `ExactSpelling` è `false`, come avviene per impostazione predefinita in C++ e C#, platform invoke cerca prima di tutto l'alias non modificato (**MessageBox**), poi il nome modificato (**MessageBoxA**) se non viene trovato l'alias non modificato. Si noti che il comportamento di corrispondenza dei nomi ANSI differisce dal comportamento di corrispondenza dei nomi Unicode.  
  
 <xref:System.Runtime.InteropServices.CharSet.Unicode>  
  
- Marshalling delle stringhe  
  
     La funzionalità platform invoke copia le stringhe dal formato gestito (Unicode) al formato Unicode.  
  
- Corrispondenza dei nomi  
  
     Quando il campo `ExactSpelling` è `true`, come per impostazione predefinita in Visual Basic, platform invoke cerca solo il nome specificato. Ad esempio, se si specifica **MessageBox**, platform invoke cerca **MessageBox** e ha esito negativo se non riesce a individuare la stringa con la stessa identica ortografia.  
  
     Quando il campo `ExactSpelling` è `false`, come avviene per impostazione predefinita in C++ e C#, platform invoke cerca prima di tutto il nome modificato (**MessageBoxW**), poi l'alias non modificato (**MessageBox**) se non viene trovato il nome modificato. Si noti che il comportamento di corrispondenza dei nomi Unicode differisce dal comportamento di corrispondenza dei nomi ANSI.  
  
 <xref:System.Runtime.InteropServices.CharSet.Auto>  
  
- La funzionalità platform invoke sceglie tra i formati ANSI e Unicode in fase di esecuzione, in base alla piattaforma di destinazione.  
  
## <a name="specify-a-character-set-in-visual-basic"></a>Specificare un set di caratteri in Visual Basic

È possibile specificare il comportamento del set di caratteri in Visual Basic aggiungendo `Ansi` la `Unicode` `Auto` parola chiave, o all'istruzione di dichiarazione. Se si omette la parola chiave set di caratteri, <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> per impostazione predefinita il campo viene impostato sul set di caratteri ANSI.

L'esempio seguente dichiara la funzione **MessageBox** tre volte, ogni volta con un diverso comportamento per il set di caratteri. La prima istruzione omette la parola chiave del set di caratteri, quindi il set di caratteri predefinito è ANSI. La seconda e la terza istruzione specificano in modo esplicito un set di caratteri con una parola chiave.

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
  
## <a name="specify-a-character-set-in-c-and-c"></a>Specificare un set di caratteri in C# e C++

Il campo <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> identifica il set di caratteri sottostante come ANSI o Unicode. Il set di caratteri controlla la modalità di marshalling degli argomenti stringa per un metodo. Usare una delle forme seguenti per indicare il set di caratteri:  
  
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
  
 L'esempio seguente mostra tre definizioni gestite della funzione **MessageBox** attribuite a un set di caratteri specifico. Nella prima definizione, con l'omissione, il campo `CharSet` usa per impostazione predefinita il set di caratteri ANSI.  
  
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
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [Creazione di prototipi nel codice gestito](creating-prototypes-in-managed-code.md)
- [Esempi di platform invoke](platform-invoke-examples.md)
- [Marshalling dei dati con platform invoke](marshaling-data-with-platform-invoke.md)
