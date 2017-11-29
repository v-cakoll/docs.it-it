---
title: Codifiche dei file (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- character encodings
- files [Visual Basic], encoding
- Unicode, file encoding
- file encoding
ms.assetid: ea2c5f5f-bbb1-4150-9928-b9951fa6bc57
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: deaab4371ab0d5d15c627bfd6352a7090bf08024
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="file-encodings-visual-basic"></a>Codifiche dei file (Visual Basic)
Le codifiche dei file, note anche come codifiche dei caratteri, specificano in che modo vengono rappresentati i caratteri durante l'elaborazione del testo. Una codifica può essere preferibile rispetto a un'altra per i caratteri del linguaggio che è o non è in grado di gestire, anche se in genere è preferibile Unicode.  
  
 Durante la lettura da o la scrittura su file, le codifiche dei file non corrispondenti possono generare eccezioni o risultati errati.  
  
## <a name="types-of-encodings"></a>Tipi di codifiche  
 Unicode è la codifica preferita quando si lavora con i file. Unicode è uno standard di codifica dei caratteri a livello mondiale che usa valori di codice a 16 bit per rappresentare tutti i caratteri usati nei sistemi informatici moderni, compresi i simboli tecnici e caratteri speciali usati per la pubblicazione.  
  
 Gli standard di codifica dei caratteri precedenti erano costituiti da set di caratteri tradizionali, ad esempio il set di caratteri ANSI di Windows che usa valori di codice a 8 bit, o combinazioni di valori a 8 bit, per rappresentare i caratteri usati in una lingua o un'area geografica specifica.  
  
## <a name="encoding-class"></a>Classe di codifica  
 La classe <xref:System.Text.Encoding> rappresenta una codifica dei caratteri. In questa tabella sono elencati i tipi di codifica disponibili con una descrizione di ogni tipo.  
  
|Nome|Descrizione|
|---|---|    
|<xref:System.Text.ASCIIEncoding>|Rappresenta una codifica dei caratteri ASCII di caratteri Unicode.|  
|<xref:System.Text.UnicodeEncoding>|Rappresenta una codifica UTF-16 dei caratteri Unicode.|  
|<xref:System.Text.UTF32Encoding>|Rappresenta una codifica UTF-32 dei caratteri Unicode.|  
|<xref:System.Text.UTF7Encoding>|Rappresenta una codifica UTF-7 dei caratteri Unicode.|  
|<xref:System.Text.UTF8Encoding>|Rappresenta una codifica UTF-8 dei caratteri Unicode.|  
  
## <a name="see-also"></a>Vedere anche  
 [Lettura da file](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)  
 [Scrittura su file](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)
