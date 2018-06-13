---
title: -imports (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- /imports compiler option [Visual Basic]
- imports compiler option [Visual Basic]
- -imports compiler option [Visual Basic]
ms.assetid: 9a93fb53-c080-497b-bf9b-441022dbbc39
ms.openlocfilehash: 330a5e6821c9c76f3503a35a5a5eabf24c686b42
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33652090"
---
# <a name="-imports-visual-basic"></a>-imports (Visual Basic)
Importa gli spazi dei nomi da un assembly specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
-imports:namespaceList  
```  
  
## <a name="arguments"></a>Argomenti  
  
|Termine|Definizione|  
|---|---|  
|`namespaceList`|Obbligatorio. Elenco delimitato da virgole degli spazi dei nomi da importare.|  
  
## <a name="remarks"></a>Note  
 Il `-imports` opzione consente di importare qualsiasi spazio dei nomi definito all'interno del gruppo di file di origine o da qualsiasi assembly di riferimento correnti.  
  
 I membri di uno spazio dei nomi specificati con `-imports` sono disponibili a tutti i file di codice sorgente nella compilazione. Utilizzare il [istruzione Imports (tipo e Namespace .NET)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) per utilizzare uno spazio dei nomi in un file di codice sorgente singolo.  
  
|Per impostare /Imports nell'ambiente di sviluppo integrato di Visual Studio|  
|---|  
|1.  Selezionare un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**. <br />2.  Fare clic sulla scheda **Riferimenti**.<br />3.  Immettere il nome dello spazio dei nomi nella casella accanto il **Aggiungi importazione utente** pulsante.<br />4.  Fare clic su di **Aggiungi importazione utente** pulsante.|  
  
## <a name="example"></a>Esempio  
 Il codice seguente viene compilato quando `/imports:system.globalization` è specificato. Senza di esso, compilazione corretta richiede che un `Imports System.Globalization` istruzione essere contenuto all'inizio del file del codice sorgente o che la proprietà essere qualificato come `System.Globalization.CultureInfo.CurrentCulture.Name`. 
  
 [!code-vb[imports example](codesnippet/VisualBasic/imports_2.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Riferimenti e istruzione Imports](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)  
 [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
