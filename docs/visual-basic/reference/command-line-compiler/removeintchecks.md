---
title: -removeintchecks
ms.date: 03/13/2018
f1_keywords:
- removeintchecks
- -removeintchecks
helpviewer_keywords:
- removeintchecks compiler option [Visual Basic]
- /removeintchecks compiler option [Visual Basic]
- -removeintchecks compiler option [Visual Basic]
ms.assetid: c1835bd5-1e38-4fba-bd2f-6984774765d4
ms.openlocfilehash: ec4722cb7088819dae95ca1b7cbc1469d957a7aa
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400474"
---
# <a name="-removeintchecks"></a>-removeintchecks
Attiva o disattiva il controllo degli errori di overflow per le operazioni integer.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a>Argomenti  
  
|Termine|Definizione|  
|---|---|  
|`+` &#124; `-`|Facoltativa. L' `-removeintchecks-` opzione fa sì che il compilatore verifichi tutti i calcoli Integer per gli errori di overflow. Il valore predefinito è `-removeintchecks-`.<br /><br /> Specifica `-removeintchecks` o `-removeintchecks+` impedisce il controllo degli errori ed è in grado di eseguire calcoli Integer più velocemente. Tuttavia, senza il controllo degli errori e in caso di overflow delle capacità del tipo di dati, i risultati non corretti possono essere archiviati senza generare un errore.|  
  
|Per impostare-removeintchecks (in Visual Studio Integrated Development Environment|  
|---|  
|1. è stato selezionato un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**. <br />2. fare clic sulla scheda **Compila** .<br />3. fare clic sul pulsante **Avanzate** .<br />4. modificare il valore della casella di **controllo Rimuovi overflow di Integer** .|  
  
## <a name="example"></a>Esempio  
 Il codice seguente compila `Test.vb` e disattiva il controllo degli errori di overflow di Integer.  
  
```console
vbc -removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](index.md)
- [Esempi di righe di comando di compilazione](sample-compilation-command-lines.md)
