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
ms.openlocfilehash: 1016a0c63a85919764271e01771ff8192341725c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="specifying-a-character-set"></a>Specifica di un set di caratteri
Il campo <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> controlla il marshalling delle stringhe e determina in che modo la funzionalità platform invoke trova i nomi di funzione in una DLL. Questo argomento descrive entrambi i comportamenti.  
  
 Alcune API esportano due versioni delle funzioni che accettano argomenti stringa: narrow (ANSI) e wide (Unicode). L'API Win32, ad esempio, include i seguenti nomi di punto di ingresso per la funzione **MessageBox**:  
  
-   **MessageBoxA**  
  
     Fornisce la formattazione ANSI dei caratteri a 1 byte, con l'aggiunta di "A" al nome del punto di ingresso per poterla distinguere. Le chiamate a **MessageBoxA** eseguono sempre il marshalling delle stringhe in formato ANSI, come è comune per le piattaforme Windows 95 e Windows 98.  
  
-   **MessageBoxW**  
  
     Fornisce la formattazione Unicode dei caratteri a 2 byte, con l'aggiunta di "W" al nome del punto di ingresso per poterla distinguere. Le chiamate a **MessageBoxW** eseguono sempre il marshalling delle stringhe in formato Unicode, come è comune per le piattaforme Windows NT, Windows 2000 e Windows XP.  
  
## <a name="string-marshaling-and-name-matching"></a>Marshalling delle stringhe e corrispondenza dei nomi  
 Il campo **CharSet** accetta i valori seguenti:  
  
 **CharSet.Ansi** (valore predefinito)  
  
-   Marshalling delle stringhe  
  
     La funzionalità platform invoke esegue il marshalling delle stringhe dal formato gestito (Unicode) al formato ANSI.  
  
-   Corrispondenza dei nomi  
  
     Quando il campo <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling?displayProperty=nameWithType> è **true**, come per impostazione predefinita in [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], platform invoke cerca solo il nome specificato. Ad esempio, se si specifica **MessageBox**, platform invoke cerca **MessageBox** e ha esito negativo quando non riesce a individuare la stringa con la stessa identica ortografia.  
  
     Quando il campo **ExactSpelling** è **false**, come avviene per impostazione predefinita in C++ e C#, platform invoke cerca prima di tutto l'alias non modificato (**MessageBox**), poi il nome modificato (**MessageBoxA**) se non viene trovato l'alias non modificato. Si noti che il comportamento di corrispondenza dei nomi ANSI differisce dal comportamento di corrispondenza dei nomi Unicode.  
  
 **CharSet.Unicode**  
  
-   Marshalling delle stringhe  
  
     La funzionalità platform invoke copia le stringhe dal formato gestito (Unicode) al formato Unicode.  
  
-   Corrispondenza dei nomi  
  
     Quando il campo **ExactSpelling** è **true**, come per impostazione predefinita in [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], platform invoke cerca solo il nome specificato. Ad esempio, se si specifica **MessageBox**, platform invoke cerca **MessageBox** e ha esito negativo se non riesce a individuare la stringa con la stessa identica ortografia.  
  
     Quando il campo **ExactSpelling** è **false**, come avviene per impostazione predefinita in C++ e C#, platform invoke cerca prima di tutto il nome modificato (**MessageBoxW**), poi l'alias non modificato (**MessageBox**) se non viene trovato il nome modificato. Si noti che il comportamento di corrispondenza dei nomi Unicode differisce dal comportamento di corrispondenza dei nomi ANSI.  
  
 **CharSet.Auto**  
  
-   La funzionalità platform invoke sceglie tra i formati ANSI e Unicode in fase di esecuzione, in base alla piattaforma di destinazione.  
  
## <a name="specifying-a-character-set-in-visual-basic"></a>Specifica un set di caratteri in Visual Basic  
 L'esempio seguente dichiara la funzione **MessageBox** tre volte, ogni volta con un diverso comportamento per il set di caratteri. È possibile specificare il comportamento per il set di caratteri in Visual Basic aggiungendo la parola chiave **Ansi**, **Unicode** o **Auto** nell'istruzione di dichiarazione.  
  
 Se si omette la parola chiave per il set di caratteri, come avviene nella prima istruzione di dichiarazione, il campo <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> usa il set di caratteri ANSI per impostazione predefinita. La seconda e la terza istruzione nell'esempio specificano in modo esplicito un set di caratteri con una parola chiave.  
  
```vb  
Imports System.Runtime.InteropServices  
  
Public Class Win32  
   Declare Function MessageBoxA Lib "user32.dll"(ByVal hWnd As Integer, _  
       ByVal txt As String, ByVal caption As String, _  
       ByVal Typ As Integer) As Integer  
  
   Declare Unicode Function MessageBoxW Lib "user32.dll" _  
       (ByVal hWnd As Integer, ByVal txt As String, _  
        ByVal caption As String, ByVal Typ As Integer) As Integer  
  
   Declare Auto Function MessageBox Lib "user32.dll" _  
       (ByVal hWnd As Integer, ByVal txt As String, _  
        ByVal caption As String, ByVal Typ As Integer) As Integer  
End Class  
```  
  
## <a name="specifying-a-character-set-in-c-and-c"></a>Specifica di un set di caratteri in C# e C++  
 Il campo <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> identifica il set di caratteri sottostante come ANSI o Unicode. Il set di caratteri controlla la modalità di marshalling degli argomenti stringa per un metodo. Usare una delle forme seguenti per indicare il set di caratteri:  
  
```csharp  
[DllImport("dllname", CharSet=CharSet.Ansi)]  
[DllImport("dllname", CharSet=CharSet.Unicode)]  
[DllImport("dllname", CharSet=CharSet.Auto)]  
```  
  
```cpp  
[DllImport("dllname", CharSet=CharSet::Ansi)]  
[DllImport("dllname", CharSet=CharSet::Unicode)]  
[DllImport("dllname", CharSet=CharSet::Auto)]  
```  
  
 L'esempio seguente mostra tre definizioni gestite della funzione **MessageBox** attribuite a un set di caratteri specifico. Nella prima definizione, con l'omissione, il campo **CharSet** usa per impostazione predefinita il set di caratteri ANSI.  
  
```csharp  
[DllImport("user32.dll")]  
    public static extern int MessageBoxA(int hWnd, String text,   
        String caption, uint type);  
[DllImport("user32.dll", CharSet=CharSet.Unicode)]  
    public static extern int MessageBoxW(int hWnd, String text,   
        String caption, uint type);  
[DllImport("user32.dll", CharSet=CharSet.Auto)]  
    public static extern int MessageBox(int hWnd, String text,   
        String caption, uint type);  
```  
  
```cpp  
typedef void* HWND;  
  
//Can use MessageBox or MessageBoxA.  
[DllImport("user32")]  
extern "C" int MessageBox(HWND hWnd,  
                          String* pText,  
                          String* pCaption,  
                          unsigned int uType);  
  
//Can use MessageBox or MessageBoxW.  
[DllImport("user32", CharSet=CharSet::Unicode)]  
extern "C" int MessageBoxW(HWND hWnd,  
                          String* pText,  
                          String* pCaption,  
                          unsigned int uType);  
  
//Must use MessageBox.  
[DllImport("user32", CharSet=CharSet::Auto)]  
extern "C" int MessageBox(HWND hWnd,  
                          String* pText,  
                          String* pCaption,  
                          unsigned int uType);  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Runtime.InteropServices.DllImportAttribute>  
 [Creazione di prototipi nel codice gestito](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)  
 [Esempi di platform invoke](../../../docs/framework/interop/platform-invoke-examples.md)  
 [Marshalling dei dati con platform invoke](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)
