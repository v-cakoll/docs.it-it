---
title: Specifica di un punto di ingresso
ms.date: 03/30/2017
helpviewer_keywords:
- EntryPoint field
- platform invoke, attribute fields
- attribute fields in platform invoke, EntryPoint
ms.assetid: d1247f08-0965-416a-b978-e0b50652dfe3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 787406b1fa7e5beb59ff3f8715c1215a734ed895
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2019
ms.locfileid: "58411304"
---
# <a name="specifying-an-entry-point"></a>Specifica di un punto di ingresso
Un punto di ingresso identifica la posizione di una funzione in una DLL. All'interno di un progetto gestito, il nome originale o il punto di ingresso ordinale di una funzione di destinazione identifica tale funzione attraverso il limite di interoperabilità. È anche possibile mappare il punto di ingresso a un nome diverso, rinominando in effetti la funzione.  
  
 L'elenco seguente include i motivi possibili per cui rinominare una funzione di DLL:  
  
-   Evitare l'uso di nomi delle funzioni API con distinzione tra maiuscole e minuscole  
  
-   Rispettare standard di denominazione esistenti  
  
-   Supportare funzioni che accettano tipi di dati diversi (dichiarando più versioni della stessa funzione di DLL)  
  
-   Semplificare l'uso delle API che includono versioni ANSI e Unicode  
  
 Questo argomento illustra come rinominare una funzione di DLL nel codice gestito.  
  
## <a name="renaming-a-function-in-visual-basic"></a>Ridenominazione di una funzione in Visual Basic  
 Visual Basic usa la parola chiave **Function** nell'istruzione **Declare** per impostare il campo <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=nameWithType>. L'esempio seguente mostra una dichiarazione di base.  
  
```vb
Imports System

Friend Class WindowsAPI
    Friend Shared Declare Auto Function MessageBox Lib "user32.dll" (
        ByVal hWnd As IntPtr,
        ByVal lpText As String,
        ByVal lpCaption As String,
        ByVal uType As UInteger) As Integer
End Class
```
  
 È possibile sostituire il punto di ingresso **MessageBox** con **MsgBox** includendo la parola chiave **Alias** nella definizione, come illustrato nell'esempio seguente. In entrambi gli esempi la parola chiave **Auto** elimina la necessità di specificare la versione del set di caratteri del punto di ingresso. Per altre informazioni sulla selezione di un set di caratteri, vedere [Specifica di un set di caratteri](../../../docs/framework/interop/specifying-a-character-set.md).  
  
```vb
Imports System

Friend Class WindowsAPI
    Friend Shared Declare Auto Function MsgBox _
        Lib "user32.dll" Alias "MessageBox" (
        ByVal hWnd As IntPtr,
        ByVal lpText As String,
        ByVal lpCaption As String,
        ByVal uType As UInteger) As Integer
End Class
```
  
## <a name="renaming-a-function-in-c-and-c"></a>Ridenominazione di una funzione in C# e C++  
 È possibile usare il campo <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=nameWithType> per specificare una funzione di DLL in base al nome o al numero ordinale. Se il nome della funzione nella definizione del metodo corrisponde al punto di ingresso nella DLL, non è necessario identificare in modo esplicito la funzione con il campo **EntryPoint**. In caso contrario, usare uno dei seguenti formati di attributo per indicare un nome o il numero ordinale:  
  
```csharp
[DllImport("DllName", EntryPoint = "Functionname")]
[DllImport("DllName", EntryPoint = "#123")]
```
  
 Si noti che è necessario anteporre il segno di cancelletto (#) a un numero ordinale.  
  
 L'esempio seguente dimostra come sostituire **MessageBoxA** con **MsgBox** nel codice usando il campo **EntryPoint**.  
  
```csharp
using System;
using System.Runtime.InteropServices;

internal static class WindowsAPI
{
    [DllImport("user32.dll", EntryPoint = "MessageBoxA")]
    internal static extern int MessageBox(
        IntPtr hWnd, string lpText, string lpCaption, uint uType);
}
```
  
```cpp
using namespace System;
using namespace System::Runtime::InteropServices;

typedef void* HWND;
[DllImport("user32", EntryPoint = "MessageBoxA")]
extern "C" int MsgBox(
    HWND hWnd, String* lpText, String* lpCaption, unsigned int uType);
```
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [Creazione di prototipi nel codice gestito](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)
- [Esempi di platform invoke](../../../docs/framework/interop/platform-invoke-examples.md)
- [Marshalling dei dati con platform invoke](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)
