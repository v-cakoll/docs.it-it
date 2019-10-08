---
title: -Imports (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- /imports compiler option [Visual Basic]
- imports compiler option [Visual Basic]
- -imports compiler option [Visual Basic]
ms.assetid: 9a93fb53-c080-497b-bf9b-441022dbbc39
ms.openlocfilehash: 929e24a1ffd02d4e21ab1b925ddd59050b5d3cc4
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005567"
---
# <a name="-imports-visual-basic"></a>-Imports (Visual Basic)
Importa gli spazi dei nomi da un assembly specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-imports:namespaceList  
```  
  
## <a name="arguments"></a>Argomenti  
  
|Nome|Definizione|  
|---|---|  
|`namespaceList`|Obbligatorio. Elenco delimitato da virgole di spazi dei nomi da importare.|  
  
## <a name="remarks"></a>Note  
 L'opzione `-imports` importa qualsiasi spazio dei nomi definito all'interno del set di file di origine corrente o da qualsiasi assembly a cui si fa riferimento.  
  
 I membri in uno spazio dei nomi specificato con `-imports` sono disponibili per tutti i file del codice sorgente nella compilazione. Usare l' [istruzione Imports (tipo e spazio dei nomi .NET)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) per usare uno spazio dei nomi in un unico file del codice sorgente.  
  
|Per impostare/Imports in Visual Studio Integrated Development Environment|  
|---|  
|1.  Selezionare un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**. <br />2.  Fare clic sulla scheda **Riferimenti**.<br />3.  Immettere il nome dello spazio dei nomi nella casella accanto al pulsante **Aggiungi importazione utente** .<br />4.  Fare clic sul pulsante **Aggiungi importazione utente** .|  
  
## <a name="example"></a>Esempio  
 Il codice seguente viene compilato quando si specifica `/imports:system.globalization`. In caso contrario, la compilazione riuscita richiede che un'istruzione `Imports System.Globalization` venga inclusa all'inizio del file di codice sorgente o che la proprietà sia completamente qualificata come `System.Globalization.CultureInfo.CurrentCulture.Name`.

```vb
Module Example
   Public Sub Main()
      Console.WriteLine($"The current culture is {CultureInfo.CurrentCulture.Name}")
   End Sub
End Module
```

## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Riferimenti e istruzione Imports](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
