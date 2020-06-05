---
title: -main
ms.date: 03/13/2018
helpviewer_keywords:
- main compiler option [Visual Basic]
- /main compiler option [Visual Basic]
- -main compiler option [Visual Basic]
ms.assetid: 83fc339d-6652-415d-b205-b5133319b5b0
ms.openlocfilehash: 5530da4c784346df4a1088998b8d2027feee08e3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403161"
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
  
## <a name="remarks"></a>Commenti  
 Usare questa opzione quando si crea un file eseguibile o un programma eseguibile di Windows. Se l'opzione **-Main** viene omessa, il compilatore cerca una condivisione valida `Sub Main` in tutti i moduli e le classi pubbliche.  
  
 Per una descrizione delle diverse forme della procedura, vedere la [procedura principale in Visual Basic](../../programming-guide/program-structure/main-procedure.md) `Main` .  
  
 Quando `location` è una classe che eredita da <xref:System.Windows.Forms.Form> , il compilatore fornisce una `Main` routine predefinita che avvia l'applicazione se la classe non ha `Main` routine. In questo modo è possibile compilare il codice dalla riga di comando creata nell'ambiente di sviluppo.  
  
 [!code-vb[VbVbalrCompiler#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/Class1.vb#16)]  
  
### <a name="to-set--main-in-the-visual-studio-integrated-development-environment"></a>Per impostare-Main in Visual Studio Integrated Development Environment  
  
1. Selezionare un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**.  
  
2. Fare clic sulla scheda **Applicazione** .  
  
3. Verificare che la casella di controllo **Abilita framework applicazione** non sia selezionata.  
  
4. Modificare il valore nella casella **oggetto di avvio** .  
  
## <a name="example"></a>Esempio  
 Il codice seguente compila `T2.vb` e `T3.vb` , specificando che la `Sub Main` stored procedure verrà trovata nella `Test2` classe.  
  
```console
vbc t2.vb t3.vb -main:Test2  
```  
  
## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](index.md)
- [-target (Visual Basic)](target.md)
- [Esempi di righe di comando di compilazione](sample-compilation-command-lines.md)
- [Routine Main in Visual Basic](../../programming-guide/program-structure/main-procedure.md)
