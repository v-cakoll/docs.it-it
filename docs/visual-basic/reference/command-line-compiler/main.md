---
title: -main
ms.date: 03/13/2018
helpviewer_keywords:
- main compiler option [Visual Basic]
- /main compiler option [Visual Basic]
- -main compiler option [Visual Basic]
ms.assetid: 83fc339d-6652-415d-b205-b5133319b5b0
ms.openlocfilehash: 91f2a27ed9b6fb296dbb9e50fc488fd012311890
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005497"
---
# <a name="-main"></a>-main
Specifica la classe o il modulo che contiene la procedura `Sub Main`.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-main:location  
```  
  
## <a name="arguments"></a>Argomenti  
 `location`  
 Obbligatorio. Nome della classe o del modulo che contiene la `Sub Main` stored procedure da chiamare all'avvio del programma. Il formato può essere **Main: module** o **-Main: Namespace. Module**.  
  
## <a name="remarks"></a>Osservazioni  
 Usare questa opzione quando si crea un file eseguibile o un programma eseguibile di Windows. Se l'opzione **-Main** viene omessa, il compilatore cerca una condivisione `Sub Main` valida in tutti i moduli e le classi pubbliche.  
  
 Per una descrizione delle diverse forme della `Main` procedura, vedere la [procedura principale in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md) .  
  
 Quando `location` è una classe che eredita da <xref:System.Windows.Forms.Form>, il compilatore fornisce una routine `Main` predefinita che avvia l'applicazione se la classe non `Main` ha routine. In questo modo è possibile compilare il codice dalla riga di comando creata nell'ambiente di sviluppo.  
  
 [!code-vb[VbVbalrCompiler#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/Class1.vb#16)]  
  
### <a name="to-set--main-in-the-visual-studio-integrated-development-environment"></a>Per impostare-Main in Visual Studio Integrated Development Environment  
  
1. Selezionare un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**.  
  
2. Fare clic sulla scheda **Applicazione** .  
  
3. Verificare che la casella di controllo **Abilita framework applicazione** non sia selezionata.  
  
4. Modificare il valore nella casella **oggetto di avvio** .  
  
## <a name="example"></a>Esempio  
 Il codice seguente `T2.vb` compila e `T3.vb`, specificando che la `Sub Main` stored procedure verrà trovata nella `Test2` classe.  
  
```console
vbc t2.vb t3.vb -main:Test2  
```  
  
## <a name="see-also"></a>Vedi anche

- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Routine Main in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md)
