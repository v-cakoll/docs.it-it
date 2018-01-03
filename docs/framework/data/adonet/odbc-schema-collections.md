---
title: Raccolte di schemi ODBC
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: b8c31f4e8b1463c184c9a8ff1cf64808783f030d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="405f8-102">Raccolte di schemi ODBC</span><span class="sxs-lookup"><span data-stu-id="405f8-102">ODBC Schema Collections</span></span>
<span data-ttu-id="405f8-103">Contenuto della sezione viene descritto il supporto delle raccolte di schemi per driver ODBC per Microsoft SQL Server, Oracle e Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="405f8-103">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="405f8-104">Driver ODBC di Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="405f8-104">Microsoft SQL Server ODBC Driver</span></span>  
 <span data-ttu-id="405f8-105">Il Driver ODBC di Microsoft SQL Server supporta le raccolte di schemi specifici seguenti oltre alle raccolte di schemi comuni:</span><span class="sxs-lookup"><span data-stu-id="405f8-105">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="405f8-106">Tabelle</span><span class="sxs-lookup"><span data-stu-id="405f8-106">Tables</span></span>  
  
-   <span data-ttu-id="405f8-107">Indexes</span><span class="sxs-lookup"><span data-stu-id="405f8-107">Indexes</span></span>  
  
-   <span data-ttu-id="405f8-108">Colonne</span><span class="sxs-lookup"><span data-stu-id="405f8-108">Columns</span></span>  
  
-   <span data-ttu-id="405f8-109">Procedure</span><span class="sxs-lookup"><span data-stu-id="405f8-109">Procedures</span></span>  
  
-   <span data-ttu-id="405f8-110">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="405f8-110">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="405f8-111">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="405f8-111">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="405f8-112">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="405f8-112">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="405f8-113">Tables e Views</span><span class="sxs-lookup"><span data-stu-id="405f8-113">Tables and Views</span></span>  
  
|<span data-ttu-id="405f8-114">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="405f8-114">ColumnName</span></span>|<span data-ttu-id="405f8-115">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="405f8-115">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="405f8-116">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="405f8-116">TABLE_CAT</span></span>|<span data-ttu-id="405f8-117">String</span><span class="sxs-lookup"><span data-stu-id="405f8-117">String</span></span>|  
|<span data-ttu-id="405f8-118">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="405f8-118">TABLE_SCHEM</span></span>|<span data-ttu-id="405f8-119">String</span><span class="sxs-lookup"><span data-stu-id="405f8-119">String</span></span>|  
|<span data-ttu-id="405f8-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="405f8-120">TABLE_NAME</span></span>|<span data-ttu-id="405f8-121">String</span><span class="sxs-lookup"><span data-stu-id="405f8-121">String</span></span>|  
|<span data-ttu-id="405f8-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="405f8-122">TABLE_TYPE</span></span>|<span data-ttu-id="405f8-123">String</span><span class="sxs-lookup"><span data-stu-id="405f8-123">String</span></span>|  
|<span data-ttu-id="405f8-124">REMARKS</span><span class="sxs-lookup"><span data-stu-id="405f8-124">REMARKS</span></span>|<span data-ttu-id="405f8-125">String</span><span class="sxs-lookup"><span data-stu-id="405f8-125">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="405f8-126">Indexes</span><span class="sxs-lookup"><span data-stu-id="405f8-126">Indexes</span></span>  
  
|<span data-ttu-id="405f8-127">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="405f8-127">ColumnName</span></span>|<span data-ttu-id="405f8-128">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="405f8-128">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="405f8-129">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="405f8-129">TABLE_CAT</span></span>|<span data-ttu-id="405f8-130">String</span><span class="sxs-lookup"><span data-stu-id="405f8-130">String</span></span>|  
|<span data-ttu-id="405f8-131">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="405f8-131">TABLE_SCHEM</span></span>|<span data-ttu-id="405f8-132">String</span><span class="sxs-lookup"><span data-stu-id="405f8-132">String</span></span>|  
|<span data-ttu-id="405f8-133">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="405f8-133">TABLE_NAME</span></span>|<span data-ttu-id="405f8-134">String</span><span class="sxs-lookup"><span data-stu-id="405f8-134">String</span></span>|  
|<span data-ttu-id="405f8-135">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="405f8-135">NON_UNIQUE</span></span>|<span data-ttu-id="405f8-136">Int16</span><span class="sxs-lookup"><span data-stu-id="405f8-136">Int16</span></span>|  
|<span data-ttu-id="405f8-137">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="405f8-137">INDEX_QUALIFIER</span></span>|<span data-ttu-id="405f8-138">String</span><span class="sxs-lookup"><span data-stu-id="405f8-138">String</span></span>|  
|<span data-ttu-id="405f8-139">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="405f8-139">INDEX_NAME</span></span>|<span data-ttu-id="405f8-140">String</span><span class="sxs-lookup"><span data-stu-id="405f8-140">String</span></span>|  
|<span data-ttu-id="405f8-141">TYPE</span><span class="sxs-lookup"><span data-stu-id="405f8-141">TYPE</span></span>|<span data-ttu-id="405f8-142">Int16</span><span class="sxs-lookup"><span data-stu-id="405f8-142">Int16</span></span>|  
|<span data-ttu-id="405f8-143">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="405f8-143">ORDINAL_POSITION</span></span>|<span data-ttu-id="405f8-144">Int16</span><span class="sxs-lookup"><span data-stu-id="405f8-144">Int16</span></span>|  
|<span data-ttu-id="405f8-145">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="405f8-145">COLUMN_NAME</span></span>|<span data-ttu-id="405f8-146">String</span><span class="sxs-lookup"><span data-stu-id="405f8-146">String</span></span>|  
|<span data-ttu-id="405f8-147">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="405f8-147">ASC_OR_DESC</span></span>|<span data-ttu-id="405f8-148">String</span><span class="sxs-lookup"><span data-stu-id="405f8-148">String</span></span>|  
|<span data-ttu-id="405f8-149">CARDINATLITY</span><span class="sxs-lookup"><span data-stu-id="405f8-149">CARDINATLITY</span></span>|<span data-ttu-id="405f8-150">Int32</span><span class="sxs-lookup"><span data-stu-id="405f8-150">Int32</span></span>|  
|<span data-ttu-id="405f8-151">PAGES</span><span class="sxs-lookup"><span data-stu-id="405f8-151">PAGES</span></span>|<span data-ttu-id="405f8-152">Int32</span><span class="sxs-lookup"><span data-stu-id="405f8-152">Int32</span></span>|  
|<span data-ttu-id="405f8-153">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="405f8-153">FILTER_CONDITION</span></span>|<span data-ttu-id="405f8-154">String</span><span class="sxs-lookup"><span data-stu-id="405f8-154">String</span></span>|  
|<span data-ttu-id="405f8-155">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="405f8-155">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="405f8-156">String</span><span class="sxs-lookup"><span data-stu-id="405f8-156">String</span></span>|  
|<span data-ttu-id="405f8-157">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="405f8-157">SS_DATA_TYPE</span></span>|<span data-ttu-id="405f8-158">Byte</span><span class="sxs-lookup"><span data-stu-id="405f8-158">Byte</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="405f8-159">Colonne</span><span class="sxs-lookup"><span data-stu-id="405f8-159">Columns</span></span>  
  
|<span data-ttu-id="405f8-160">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="405f8-160">ColumnName</span></span>|<span data-ttu-id="405f8-161">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="405f8-161">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="405f8-162">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="405f8-162">TABLE_CAT</span></span>|<span data-ttu-id="405f8-163">String</span><span class="sxs-lookup"><span data-stu-id="405f8-163">String</span></span>|  
|<span data-ttu-id="405f8-164">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="405f8-164">TABLE_SCHEM</span></span>|<span data-ttu-id="405f8-165">String</span><span class="sxs-lookup"><span data-stu-id="405f8-165">String</span></span>|  
|<span data-ttu-id="405f8-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="405f8-166">TABLE_NAME</span></span>|<span data-ttu-id="405f8-167">String</span><span class="sxs-lookup"><span data-stu-id="405f8-167">String</span></span>|  
|<span data-ttu-id="405f8-168">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="405f8-168">COLUMN_NAME</span></span>|<span data-ttu-id="405f8-169">String</span><span class="sxs-lookup"><span data-stu-id="405f8-169">String</span></span>|  
|<span data-ttu-id="405f8-170">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="405f8-170">DATA_TYPE</span></span>|<span data-ttu-id="405f8-171">Int16</span><span class="sxs-lookup"><span data-stu-id="405f8-171">Int16</span></span>|  
|<span data-ttu-id="405f8-172">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="405f8-172">TYPE_NAME</span></span>|<span data-ttu-id="405f8-173">String</span><span class="sxs-lookup"><span data-stu-id="405f8-173">String</span></span>|  
|<span data-ttu-id="405f8-174">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="405f8-174">COLUMN_SIZE</span></span>|<span data-ttu-id="405f8-175">Int32</span><span class="sxs-lookup"><span data-stu-id="405f8-175">Int32</span></span>|  
|<span data-ttu-id="405f8-176">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="405f8-176">BUFFER_LENGTH</span></span>|<span data-ttu-id="405f8-177">Int32</span><span class="sxs-lookup"><span data-stu-id="405f8-177">Int32</span></span>|  
|<span data-ttu-id="405f8-178">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="405f8-178">DECIMAL_DIGITS</span></span>|<span data-ttu-id="405f8-179">Int16</span><span class="sxs-lookup"><span data-stu-id="405f8-179">Int16</span></span>|  
|<span data-ttu-id="405f8-180">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="405f8-180">NUM_PREC_RADIX</span></span>|<span data-ttu-id="405f8-181">Int16</span><span class="sxs-lookup"><span data-stu-id="405f8-181">Int16</span></span>|  
|<span data-ttu-id="405f8-182">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="405f8-182">NULLABLE</span></span>|<span data-ttu-id="405f8-183">Int16</span><span class="sxs-lookup"><span data-stu-id="405f8-183">Int16</span></span>|  
|<span data-ttu-id="405f8-184">REMARKS</span><span class="sxs-lookup"><span data-stu-id="405f8-184">REMARKS</span></span>|<span data-ttu-id="405f8-185">String</span><span class="sxs-lookup"><span data-stu-id="405f8-185">String</span></span>|  
|<span data-ttu-id="405f8-186">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="405f8-186">COLUMN_DEF</span></span>|<span data-ttu-id="405f8-187">String</span><span class="sxs-lookup"><span data-stu-id="405f8-187">String</span></span>|  
|<span data-ttu-id="405f8-188">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="405f8-188">SQL_DATA_TYPE</span></span>|<span data-ttu-id="405f8-189">Int16</span><span class="sxs-lookup"><span data-stu-id="405f8-189">Int16</span></span>|  
|<span data-ttu-id="405f8-190">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="405f8-190">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="405f8-191">Int16</span><span class="sxs-lookup"><span data-stu-id="405f8-191">Int16</span></span>|  
|<span data-ttu-id="405f8-192">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="405f8-192">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="405f8-193">Int32</span><span class="sxs-lookup"><span data-stu-id="405f8-193">Int32</span></span>|  
|<span data-ttu-id="405f8-194">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="405f8-194">ORDINAL_POSITION</span></span>|<span data-ttu-id="405f8-195">Int32</span><span class="sxs-lookup"><span data-stu-id="405f8-195">Int32</span></span>|  
|<span data-ttu-id="405f8-196">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="405f8-196">IS_NULLABLE</span></span>|<span data-ttu-id="405f8-197">String</span><span class="sxs-lookup"><span data-stu-id="405f8-197">String</span></span>|  
|<span data-ttu-id="405f8-198">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="405f8-198">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="405f8-199">String</span><span class="sxs-lookup"><span data-stu-id="405f8-199">String</span></span>|  
|<span data-ttu-id="405f8-200">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="405f8-200">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="405f8-201">String</span><span class="sxs-lookup"><span data-stu-id="405f8-201">String</span></span>|  
|<span data-ttu-id="405f8-202">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="405f8-202">SS_DATA_TYPE</span></span>|<span data-ttu-id="405f8-203">Byte</span><span class="sxs-lookup"><span data-stu-id="405f8-203">Byte</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="405f8-204">Procedure</span><span class="sxs-lookup"><span data-stu-id="405f8-204">Procedures</span></span>  
  
|<span data-ttu-id="405f8-205">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="405f8-205">ColumnName</span></span>|<span data-ttu-id="405f8-206">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="405f8-206">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="405f8-207">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="405f8-207">PROCEDURE_CAT</span></span>|<span data-ttu-id="405f8-208">String</span><span class="sxs-lookup"><span data-stu-id="405f8-208">String</span></span>|  
|<span data-ttu-id="405f8-209">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="405f8-209">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="405f8-210">String</span><span class="sxs-lookup"><span data-stu-id="405f8-210">String</span></span>|  
|<span data-ttu-id="405f8-211">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="405f8-211">PROCEDURE_NAME</span></span>|<span data-ttu-id="405f8-212">String</span><span class="sxs-lookup"><span data-stu-id="405f8-212">String</span></span>|  
|<span data-ttu-id="405f8-213">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="405f8-213">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="405f8-214">Int32</span><span class="sxs-lookup"><span data-stu-id="405f8-214">Int32</span></span>|  
|<span data-ttu-id="405f8-215">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="405f8-215">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="405f8-216">Int32</span><span class="sxs-lookup"><span data-stu-id="405f8-216">Int32</span></span>|  
|<span data-ttu-id="405f8-217">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="405f8-217">NUM_RESULT_SETS</span></span>|<span data-ttu-id="405f8-218">Int32</span><span class="sxs-lookup"><span data-stu-id="405f8-218">Int32</span></span>|  
|<span data-ttu-id="405f8-219">REMARKS</span><span class="sxs-lookup"><span data-stu-id="405f8-219">REMARKS</span></span>|<span data-ttu-id="405f8-220">String</span><span class="sxs-lookup"><span data-stu-id="405f8-220">String</span></span>|  
|<span data-ttu-id="405f8-221">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="405f8-221">PROCEDURE_TYPE</span></span>|<span data-ttu-id="405f8-222">Int16</span><span class="sxs-lookup"><span data-stu-id="405f8-222">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="405f8-223">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="405f8-223">ProcedureColumns</span></span>  
  
|<span data-ttu-id="405f8-224">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="405f8-224">ColumnName</span></span>|<span data-ttu-id="405f8-225">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="405f8-225">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="405f8-226">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="405f8-226">PROCEDURE_CAT</span></span>|<span data-ttu-id="405f8-227">String</span><span class="sxs-lookup"><span data-stu-id="405f8-227">String</span></span>|  
|<span data-ttu-id="405f8-228">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="405f8-228">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="405f8-229">String</span><span class="sxs-lookup"><span data-stu-id="405f8-229">String</span></span>|  
|<span data-ttu-id="405f8-230">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="405f8-230">PROCEDURE_NAME</span></span>|<span data-ttu-id="405f8-231">String</span><span class="sxs-lookup"><span data-stu-id="405f8-231">String</span></span>|  
|<span data-ttu-id="405f8-232">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="405f8-232">COLUMN_NAME</span></span>|<span data-ttu-id="405f8-233">String</span><span class="sxs-lookup"><span data-stu-id="405f8-233">String</span></span>|  
|<span data-ttu-id="405f8-234">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="405f8-234">COLUMN_TYPE</span></span>|<span data-ttu-id="405f8-235">Int16</span><span class="sxs-lookup"><span data-stu-id="405f8-235">Int16</span></span>|  
|<span data-ttu-id="405f8-236">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="405f8-236">DATA_TYPE</span></span>|<span data-ttu-id="405f8-237">Int16</span><span class="sxs-lookup"><span data-stu-id="405f8-237">Int16</span></span>|  
|<span data-ttu-id="405f8-238">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="405f8-238">TYPE_NAME</span></span>|<span data-ttu-id="405f8-239">String</span><span class="sxs-lookup"><span data-stu-id="405f8-239">String</span></span>|  
|<span data-ttu-id="405f8-240">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="405f8-240">COLUMN_SIZE</span></span>|<span data-ttu-id="405f8-241">Int32</span><span class="sxs-lookup"><span data-stu-id="405f8-241">Int32</span></span>|  
|<span data-ttu-id="405f8-242">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="405f8-242">BUFFER_LENGTH</span></span>|<span data-ttu-id="405f8-243">Int32</span><span class="sxs-lookup"><span data-stu-id="405f8-243">Int32</span></span>|  
|<span data-ttu-id="405f8-244">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="405f8-244">DECIMAL_DIGITS</span></span>|<span data-ttu-id="405f8-245">Int16</span><span class="sxs-lookup"><span data-stu-id="405f8-245">Int16</span></span>|  
|<span data-ttu-id="405f8-246">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="405f8-246">NUM_PREC_RADIX</span></span>|<span data-ttu-id="405f8-247">Int16</span><span class="sxs-lookup"><span data-stu-id="405f8-247">Int16</span></span>|  
|<span data-ttu-id="405f8-248">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="405f8-248">NULLABLE</span></span>|<span data-ttu-id="405f8-249">Int16</span><span class="sxs-lookup"><span data-stu-id="405f8-249">Int16</span></span>|  
|<span data-ttu-id="405f8-250">REMARKS</span><span class="sxs-lookup"><span data-stu-id="405f8-250">REMARKS</span></span>|<span data-ttu-id="405f8-251">String</span><span class="sxs-lookup"><span data-stu-id="405f8-251">String</span></span>|  
|<span data-ttu-id="405f8-252">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="405f8-252">COLUMN_DEF</span></span>|<span data-ttu-id="405f8-253">String</span><span class="sxs-lookup"><span data-stu-id="405f8-253">String</span></span>|  
|<span data-ttu-id="405f8-254">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="405f8-254">SQL_DATA_TYPE</span></span>|<span data-ttu-id="405f8-255">Int16</span><span class="sxs-lookup"><span data-stu-id="405f8-255">Int16</span></span>|  
|<span data-ttu-id="405f8-256">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="405f8-256">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="405f8-257">Int16</span><span class="sxs-lookup"><span data-stu-id="405f8-257">Int16</span></span>|  
|<span data-ttu-id="405f8-258">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="405f8-258">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="405f8-259">Int32</span><span class="sxs-lookup"><span data-stu-id="405f8-259">Int32</span></span>|  
|<span data-ttu-id="405f8-260">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="405f8-260">ORDINAL_POSITION</span></span>|<span data-ttu-id="405f8-261">Int32</span><span class="sxs-lookup"><span data-stu-id="405f8-261">Int32</span></span>|  
|<span data-ttu-id="405f8-262">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="405f8-262">IS_NULLABLE</span></span>|<span data-ttu-id="405f8-263">String</span><span class="sxs-lookup"><span data-stu-id="405f8-263">String</span></span>|  
|<span data-ttu-id="405f8-264">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="405f8-264">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="405f8-265">String</span><span class="sxs-lookup"><span data-stu-id="405f8-265">String</span></span>|  
|<span data-ttu-id="405f8-266">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="405f8-266">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="405f8-267">String</span><span class="sxs-lookup"><span data-stu-id="405f8-267">String</span></span>|  
|<span data-ttu-id="405f8-268">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="405f8-268">SS_DATA_TYPE</span></span>|<span data-ttu-id="405f8-269">Byte</span><span class="sxs-lookup"><span data-stu-id="405f8-269">Byte</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="405f8-270">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="405f8-270">ProcedureParameters</span></span>  
  
|<span data-ttu-id="405f8-271">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="405f8-271">ColumnName</span></span>|<span data-ttu-id="405f8-272">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="405f8-272">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="405f8-273">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="405f8-273">PROCEDURE_CAT</span></span>|<span data-ttu-id="405f8-274">String</span><span class="sxs-lookup"><span data-stu-id="405f8-274">String</span></span>|  
|<span data-ttu-id="405f8-275">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="405f8-275">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="405f8-276">String</span><span class="sxs-lookup"><span data-stu-id="405f8-276">String</span></span>|  
|<span data-ttu-id="405f8-277">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="405f8-277">PROCEDURE_NAME</span></span>|<span data-ttu-id="405f8-278">String</span><span class="sxs-lookup"><span data-stu-id="405f8-278">String</span></span>|  
|<span data-ttu-id="405f8-279">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="405f8-279">COLUMN_NAME</span></span>|<span data-ttu-id="405f8-280">String</span><span class="sxs-lookup"><span data-stu-id="405f8-280">String</span></span>|  
|<span data-ttu-id="405f8-281">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="405f8-281">COLUMN_TYPE</span></span>|<span data-ttu-id="405f8-282">Int16</span><span class="sxs-lookup"><span data-stu-id="405f8-282">Int16</span></span>|  
|<span data-ttu-id="405f8-283">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="405f8-283">DATA_TYPE</span></span>|<span data-ttu-id="405f8-284">Int16</span><span class="sxs-lookup"><span data-stu-id="405f8-284">Int16</span></span>|  
|<span data-ttu-id="405f8-285">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="405f8-285">TYPE_NAME</span></span>|<span data-ttu-id="405f8-286">String</span><span class="sxs-lookup"><span data-stu-id="405f8-286">String</span></span>|  
|<span data-ttu-id="405f8-287">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="405f8-287">COLUMN_SIZE</span></span>|<span data-ttu-id="405f8-288">Int32</span><span class="sxs-lookup"><span data-stu-id="405f8-288">Int32</span></span>|  
|<span data-ttu-id="405f8-289">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="405f8-289">BUFFER_LENGTH</span></span>|<span data-ttu-id="405f8-290">Int32</span><span class="sxs-lookup"><span data-stu-id="405f8-290">Int32</span></span>|  
|<span data-ttu-id="405f8-291">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="405f8-291">DECIMAL_DIGITS</span></span>|<span data-ttu-id="405f8-292">Int16</span><span class="sxs-lookup"><span data-stu-id="405f8-292">Int16</span></span>|  
|<span data-ttu-id="405f8-293">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="405f8-293">NUM_PREC_RADIX</span></span>|<span data-ttu-id="405f8-294">Int16</span><span class="sxs-lookup"><span data-stu-id="405f8-294">Int16</span></span>|  
|<span data-ttu-id="405f8-295">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="405f8-295">NULLABLE</span></span>|<span data-ttu-id="405f8-296">Int16</span><span class="sxs-lookup"><span data-stu-id="405f8-296">Int16</span></span>|  
|<span data-ttu-id="405f8-297">REMARKS</span><span class="sxs-lookup"><span data-stu-id="405f8-297">REMARKS</span></span>|<span data-ttu-id="405f8-298">String</span><span class="sxs-lookup"><span data-stu-id="405f8-298">String</span></span>|  
|<span data-ttu-id="405f8-299">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="405f8-299">COLUMN_DEF</span></span>|<span data-ttu-id="405f8-300">String</span><span class="sxs-lookup"><span data-stu-id="405f8-300">String</span></span>|  
|<span data-ttu-id="405f8-301">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="405f8-301">SQL_DATA_TYPE</span></span>|<span data-ttu-id="405f8-302">Int16</span><span class="sxs-lookup"><span data-stu-id="405f8-302">Int16</span></span>|  
|<span data-ttu-id="405f8-303">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="405f8-303">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="405f8-304">Int16</span><span class="sxs-lookup"><span data-stu-id="405f8-304">Int16</span></span>|  
|<span data-ttu-id="405f8-305">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="405f8-305">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="405f8-306">Int32</span><span class="sxs-lookup"><span data-stu-id="405f8-306">Int32</span></span>|  
|<span data-ttu-id="405f8-307">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="405f8-307">ORDINAL_POSITION</span></span>|<span data-ttu-id="405f8-308">Int32</span><span class="sxs-lookup"><span data-stu-id="405f8-308">Int32</span></span>|  
|<span data-ttu-id="405f8-309">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="405f8-309">IS_NULLABLE</span></span>|<span data-ttu-id="405f8-310">String</span><span class="sxs-lookup"><span data-stu-id="405f8-310">String</span></span>|  
|<span data-ttu-id="405f8-311">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="405f8-311">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="405f8-312">String</span><span class="sxs-lookup"><span data-stu-id="405f8-312">String</span></span>|  
|<span data-ttu-id="405f8-313">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="405f8-313">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="405f8-314">String</span><span class="sxs-lookup"><span data-stu-id="405f8-314">String</span></span>|  
|<span data-ttu-id="405f8-315">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="405f8-315">SS_DATA_TYPE</span></span>|<span data-ttu-id="405f8-316">Byte</span><span class="sxs-lookup"><span data-stu-id="405f8-316">Byte</span></span>|  
  
## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="405f8-317">Driver Microsoft ODBC per Oracle</span><span class="sxs-lookup"><span data-stu-id="405f8-317">Microsoft Oracle ODBC Driver</span></span>  
 <span data-ttu-id="405f8-318">Il Driver ODBC di Microsoft SQL Server Oracle supporta le raccolte di schemi specifici seguenti oltre alle raccolte di schemi comuni:</span><span class="sxs-lookup"><span data-stu-id="405f8-318">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="405f8-319">Tabelle</span><span class="sxs-lookup"><span data-stu-id="405f8-319">Tables</span></span>  
  
-   <span data-ttu-id="405f8-320">Colonne</span><span class="sxs-lookup"><span data-stu-id="405f8-320">Columns</span></span>  
  
-   <span data-ttu-id="405f8-321">Procedure</span><span class="sxs-lookup"><span data-stu-id="405f8-321">Procedures</span></span>  
  
-   <span data-ttu-id="405f8-322">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="405f8-322">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="405f8-323">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="405f8-323">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="405f8-324">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="405f8-324">Views</span></span>  
  
-   <span data-ttu-id="405f8-325">Indexes</span><span class="sxs-lookup"><span data-stu-id="405f8-325">Indexes</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="405f8-326">Tables e Views</span><span class="sxs-lookup"><span data-stu-id="405f8-326">Tables and Views</span></span>  
  
|<span data-ttu-id="405f8-327">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="405f8-327">ColumnName</span></span>|<span data-ttu-id="405f8-328">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="405f8-328">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="405f8-329">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="405f8-329">TABLE_QUALIFIER</span></span>|<span data-ttu-id="405f8-330">String</span><span class="sxs-lookup"><span data-stu-id="405f8-330">String</span></span>|  
|<span data-ttu-id="405f8-331">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="405f8-331">TABLE_OWNER</span></span>|<span data-ttu-id="405f8-332">String</span><span class="sxs-lookup"><span data-stu-id="405f8-332">String</span></span>|  
|<span data-ttu-id="405f8-333">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="405f8-333">TABLE_NAME</span></span>|<span data-ttu-id="405f8-334">String</span><span class="sxs-lookup"><span data-stu-id="405f8-334">String</span></span>|  
|<span data-ttu-id="405f8-335">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="405f8-335">TABLE_TYPE</span></span>|<span data-ttu-id="405f8-336">String</span><span class="sxs-lookup"><span data-stu-id="405f8-336">String</span></span>|  
|<span data-ttu-id="405f8-337">REMARKS</span><span class="sxs-lookup"><span data-stu-id="405f8-337">REMARKS</span></span>|<span data-ttu-id="405f8-338">String</span><span class="sxs-lookup"><span data-stu-id="405f8-338">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="405f8-339">Colonne</span><span class="sxs-lookup"><span data-stu-id="405f8-339">Columns</span></span>  
  
|<span data-ttu-id="405f8-340">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="405f8-340">ColumnName</span></span>|<span data-ttu-id="405f8-341">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="405f8-341">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="405f8-342">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="405f8-342">TABLE_QUALIFIER</span></span>|<span data-ttu-id="405f8-343">String</span><span class="sxs-lookup"><span data-stu-id="405f8-343">String</span></span>|  
|<span data-ttu-id="405f8-344">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="405f8-344">TABLE_OWNER</span></span>|<span data-ttu-id="405f8-345">String</span><span class="sxs-lookup"><span data-stu-id="405f8-345">String</span></span>|  
|<span data-ttu-id="405f8-346">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="405f8-346">TABLE_NAME</span></span>|<span data-ttu-id="405f8-347">String</span><span class="sxs-lookup"><span data-stu-id="405f8-347">String</span></span>|  
|<span data-ttu-id="405f8-348">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="405f8-348">COLUMN_NAME</span></span>|<span data-ttu-id="405f8-349">String</span><span class="sxs-lookup"><span data-stu-id="405f8-349">String</span></span>|  
|<span data-ttu-id="405f8-350">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="405f8-350">DATA_TYPE</span></span>|<span data-ttu-id="405f8-351">Int16</span><span class="sxs-lookup"><span data-stu-id="405f8-351">Int16</span></span>|  
|<span data-ttu-id="405f8-352">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="405f8-352">TYPE_NAME</span></span>|<span data-ttu-id="405f8-353">String</span><span class="sxs-lookup"><span data-stu-id="405f8-353">String</span></span>|  
|<span data-ttu-id="405f8-354">PRECISION</span><span class="sxs-lookup"><span data-stu-id="405f8-354">PRECISION</span></span>|<span data-ttu-id="405f8-355">Int32</span><span class="sxs-lookup"><span data-stu-id="405f8-355">Int32</span></span>|  
|<span data-ttu-id="405f8-356">LENGTH</span><span class="sxs-lookup"><span data-stu-id="405f8-356">LENGTH</span></span>|<span data-ttu-id="405f8-357">Int32</span><span class="sxs-lookup"><span data-stu-id="405f8-357">Int32</span></span>|  
|<span data-ttu-id="405f8-358">SCALE</span><span class="sxs-lookup"><span data-stu-id="405f8-358">SCALE</span></span>|<span data-ttu-id="405f8-359">Int16</span><span class="sxs-lookup"><span data-stu-id="405f8-359">Int16</span></span>|  
|<span data-ttu-id="405f8-360">RADIX</span><span class="sxs-lookup"><span data-stu-id="405f8-360">RADIX</span></span>|<span data-ttu-id="405f8-361">Int16</span><span class="sxs-lookup"><span data-stu-id="405f8-361">Int16</span></span>|  
|<span data-ttu-id="405f8-362">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="405f8-362">NULLABLE</span></span>|<span data-ttu-id="405f8-363">Int16</span><span class="sxs-lookup"><span data-stu-id="405f8-363">Int16</span></span>|  
|<span data-ttu-id="405f8-364">REMARKS</span><span class="sxs-lookup"><span data-stu-id="405f8-364">REMARKS</span></span>|<span data-ttu-id="405f8-365">String</span><span class="sxs-lookup"><span data-stu-id="405f8-365">String</span></span>|  
|<span data-ttu-id="405f8-366">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="405f8-366">ORDINAL_POSITION</span></span>|<span data-ttu-id="405f8-367">Int32</span><span class="sxs-lookup"><span data-stu-id="405f8-367">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="405f8-368">Procedure</span><span class="sxs-lookup"><span data-stu-id="405f8-368">Procedures</span></span>  
  
|<span data-ttu-id="405f8-369">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="405f8-369">ColumnName</span></span>|<span data-ttu-id="405f8-370">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="405f8-370">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="405f8-371">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="405f8-371">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="405f8-372">String</span><span class="sxs-lookup"><span data-stu-id="405f8-372">String</span></span>|  
|<span data-ttu-id="405f8-373">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="405f8-373">PROCEDURE_OWNER</span></span>|<span data-ttu-id="405f8-374">String</span><span class="sxs-lookup"><span data-stu-id="405f8-374">String</span></span>|  
|<span data-ttu-id="405f8-375">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="405f8-375">PROCEDURE_NAME</span></span>|<span data-ttu-id="405f8-376">String</span><span class="sxs-lookup"><span data-stu-id="405f8-376">String</span></span>|  
|<span data-ttu-id="405f8-377">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="405f8-377">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="405f8-378">Int16</span><span class="sxs-lookup"><span data-stu-id="405f8-378">Int16</span></span>|  
|<span data-ttu-id="405f8-379">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="405f8-379">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="405f8-380">Int16</span><span class="sxs-lookup"><span data-stu-id="405f8-380">Int16</span></span>|  
|<span data-ttu-id="405f8-381">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="405f8-381">NUM_RESULT_SETS</span></span>|<span data-ttu-id="405f8-382">Int16</span><span class="sxs-lookup"><span data-stu-id="405f8-382">Int16</span></span>|  
|<span data-ttu-id="405f8-383">REMARKS</span><span class="sxs-lookup"><span data-stu-id="405f8-383">REMARKS</span></span>|<span data-ttu-id="405f8-384">String</span><span class="sxs-lookup"><span data-stu-id="405f8-384">String</span></span>|  
|<span data-ttu-id="405f8-385">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="405f8-385">PROCEDURE_TYPE</span></span>|<span data-ttu-id="405f8-386">Int16</span><span class="sxs-lookup"><span data-stu-id="405f8-386">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="405f8-387">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="405f8-387">ProcedureColumns</span></span>  
  
|<span data-ttu-id="405f8-388">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="405f8-388">ColumnName</span></span>|<span data-ttu-id="405f8-389">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="405f8-389">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="405f8-390">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="405f8-390">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="405f8-391">String</span><span class="sxs-lookup"><span data-stu-id="405f8-391">String</span></span>|  
|<span data-ttu-id="405f8-392">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="405f8-392">PROCEDURE_OWNER</span></span>|<span data-ttu-id="405f8-393">String</span><span class="sxs-lookup"><span data-stu-id="405f8-393">String</span></span>|  
|<span data-ttu-id="405f8-394">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="405f8-394">PROCEDURE_NAME</span></span>|<span data-ttu-id="405f8-395">String</span><span class="sxs-lookup"><span data-stu-id="405f8-395">String</span></span>|  
|<span data-ttu-id="405f8-396">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="405f8-396">COLUMN_NAME</span></span>|<span data-ttu-id="405f8-397">String</span><span class="sxs-lookup"><span data-stu-id="405f8-397">String</span></span>|  
|<span data-ttu-id="405f8-398">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="405f8-398">COLUMN_TYPE</span></span>|<span data-ttu-id="405f8-399">Int16</span><span class="sxs-lookup"><span data-stu-id="405f8-399">Int16</span></span>|  
|<span data-ttu-id="405f8-400">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="405f8-400">DATA_TYPE</span></span>|<span data-ttu-id="405f8-401">Int16</span><span class="sxs-lookup"><span data-stu-id="405f8-401">Int16</span></span>|  
|<span data-ttu-id="405f8-402">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="405f8-402">TYPE_NAME</span></span>|<span data-ttu-id="405f8-403">String</span><span class="sxs-lookup"><span data-stu-id="405f8-403">String</span></span>|  
|<span data-ttu-id="405f8-404">PRECISION</span><span class="sxs-lookup"><span data-stu-id="405f8-404">PRECISION</span></span>|<span data-ttu-id="405f8-405">Int32</span><span class="sxs-lookup"><span data-stu-id="405f8-405">Int32</span></span>|  
|<span data-ttu-id="405f8-406">LENGTH</span><span class="sxs-lookup"><span data-stu-id="405f8-406">LENGTH</span></span>|<span data-ttu-id="405f8-407">Int32</span><span class="sxs-lookup"><span data-stu-id="405f8-407">Int32</span></span>|  
|<span data-ttu-id="405f8-408">SCALE</span><span class="sxs-lookup"><span data-stu-id="405f8-408">SCALE</span></span>|<span data-ttu-id="405f8-409">Int16</span><span class="sxs-lookup"><span data-stu-id="405f8-409">Int16</span></span>|  
|<span data-ttu-id="405f8-410">RADIX</span><span class="sxs-lookup"><span data-stu-id="405f8-410">RADIX</span></span>|<span data-ttu-id="405f8-411">Int16</span><span class="sxs-lookup"><span data-stu-id="405f8-411">Int16</span></span>|  
|<span data-ttu-id="405f8-412">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="405f8-412">NULLABLE</span></span>|<span data-ttu-id="405f8-413">Int16</span><span class="sxs-lookup"><span data-stu-id="405f8-413">Int16</span></span>|  
|<span data-ttu-id="405f8-414">REMARKS</span><span class="sxs-lookup"><span data-stu-id="405f8-414">REMARKS</span></span>|<span data-ttu-id="405f8-415">String</span><span class="sxs-lookup"><span data-stu-id="405f8-415">String</span></span>|  
|<span data-ttu-id="405f8-416">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="405f8-416">OVERLOAD</span></span>|<span data-ttu-id="405f8-417">Int32</span><span class="sxs-lookup"><span data-stu-id="405f8-417">Int32</span></span>|  
|<span data-ttu-id="405f8-418">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="405f8-418">ORDINAL_POSITION</span></span>|<span data-ttu-id="405f8-419">Int32</span><span class="sxs-lookup"><span data-stu-id="405f8-419">Int32</span></span>|  
  
## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="405f8-420">Driver ODBC per Microsoft Jet</span><span class="sxs-lookup"><span data-stu-id="405f8-420">Microsoft Jet ODBC Driver</span></span>  
 <span data-ttu-id="405f8-421">Oltre alle raccolte di schemi comuni, il driver ODBC per Microsoft Jet supporta le raccolte di schemi specifici seguenti:</span><span class="sxs-lookup"><span data-stu-id="405f8-421">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="405f8-422">Tabelle</span><span class="sxs-lookup"><span data-stu-id="405f8-422">Tables</span></span>  
  
-   <span data-ttu-id="405f8-423">Indexes</span><span class="sxs-lookup"><span data-stu-id="405f8-423">Indexes</span></span>  
  
-   <span data-ttu-id="405f8-424">Colonne</span><span class="sxs-lookup"><span data-stu-id="405f8-424">Columns</span></span>  
  
-   <span data-ttu-id="405f8-425">Procedure</span><span class="sxs-lookup"><span data-stu-id="405f8-425">Procedures</span></span>  
  
-   <span data-ttu-id="405f8-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="405f8-426">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="405f8-427">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="405f8-427">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="405f8-428">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="405f8-428">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="405f8-429">Tables e Views</span><span class="sxs-lookup"><span data-stu-id="405f8-429">Tables and Views</span></span>  
  
|<span data-ttu-id="405f8-430">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="405f8-430">ColumnName</span></span>|<span data-ttu-id="405f8-431">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="405f8-431">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="405f8-432">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="405f8-432">TABLE_QUALIFIER</span></span>|<span data-ttu-id="405f8-433">String</span><span class="sxs-lookup"><span data-stu-id="405f8-433">String</span></span>|  
|<span data-ttu-id="405f8-434">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="405f8-434">TABLE_OWNER</span></span>|<span data-ttu-id="405f8-435">String</span><span class="sxs-lookup"><span data-stu-id="405f8-435">String</span></span>|  
|<span data-ttu-id="405f8-436">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="405f8-436">TABLE_NAME</span></span>|<span data-ttu-id="405f8-437">String</span><span class="sxs-lookup"><span data-stu-id="405f8-437">String</span></span>|  
|<span data-ttu-id="405f8-438">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="405f8-438">TABLE_TYPE</span></span>|<span data-ttu-id="405f8-439">String</span><span class="sxs-lookup"><span data-stu-id="405f8-439">String</span></span>|  
|<span data-ttu-id="405f8-440">REMARKS</span><span class="sxs-lookup"><span data-stu-id="405f8-440">REMARKS</span></span>|<span data-ttu-id="405f8-441">String</span><span class="sxs-lookup"><span data-stu-id="405f8-441">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="405f8-442">Colonne</span><span class="sxs-lookup"><span data-stu-id="405f8-442">Columns</span></span>  
  
|<span data-ttu-id="405f8-443">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="405f8-443">ColumnName</span></span>|<span data-ttu-id="405f8-444">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="405f8-444">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="405f8-445">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="405f8-445">TABLE_QUALIFIER</span></span>|<span data-ttu-id="405f8-446">String</span><span class="sxs-lookup"><span data-stu-id="405f8-446">String</span></span>|  
|<span data-ttu-id="405f8-447">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="405f8-447">TABLE_OWNER</span></span>|<span data-ttu-id="405f8-448">String</span><span class="sxs-lookup"><span data-stu-id="405f8-448">String</span></span>|  
|<span data-ttu-id="405f8-449">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="405f8-449">TABLE_NAME</span></span>|<span data-ttu-id="405f8-450">String</span><span class="sxs-lookup"><span data-stu-id="405f8-450">String</span></span>|  
|<span data-ttu-id="405f8-451">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="405f8-451">COLUMN_NAME</span></span>|<span data-ttu-id="405f8-452">String</span><span class="sxs-lookup"><span data-stu-id="405f8-452">String</span></span>|  
|<span data-ttu-id="405f8-453">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="405f8-453">DATA_TYPE</span></span>|<span data-ttu-id="405f8-454">Int16</span><span class="sxs-lookup"><span data-stu-id="405f8-454">Int16</span></span>|  
|<span data-ttu-id="405f8-455">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="405f8-455">TYPE_NAME</span></span>|<span data-ttu-id="405f8-456">String</span><span class="sxs-lookup"><span data-stu-id="405f8-456">String</span></span>|  
|<span data-ttu-id="405f8-457">PRECISION</span><span class="sxs-lookup"><span data-stu-id="405f8-457">PRECISION</span></span>|<span data-ttu-id="405f8-458">Int32</span><span class="sxs-lookup"><span data-stu-id="405f8-458">Int32</span></span>|  
|<span data-ttu-id="405f8-459">LENGTH</span><span class="sxs-lookup"><span data-stu-id="405f8-459">LENGTH</span></span>|<span data-ttu-id="405f8-460">Int32</span><span class="sxs-lookup"><span data-stu-id="405f8-460">Int32</span></span>|  
|<span data-ttu-id="405f8-461">SCALE</span><span class="sxs-lookup"><span data-stu-id="405f8-461">SCALE</span></span>|<span data-ttu-id="405f8-462">Int16</span><span class="sxs-lookup"><span data-stu-id="405f8-462">Int16</span></span>|  
|<span data-ttu-id="405f8-463">RADIX</span><span class="sxs-lookup"><span data-stu-id="405f8-463">RADIX</span></span>|<span data-ttu-id="405f8-464">Int16</span><span class="sxs-lookup"><span data-stu-id="405f8-464">Int16</span></span>|  
|<span data-ttu-id="405f8-465">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="405f8-465">NULLABLE</span></span>|<span data-ttu-id="405f8-466">Int16</span><span class="sxs-lookup"><span data-stu-id="405f8-466">Int16</span></span>|  
|<span data-ttu-id="405f8-467">REMARKS</span><span class="sxs-lookup"><span data-stu-id="405f8-467">REMARKS</span></span>|<span data-ttu-id="405f8-468">String</span><span class="sxs-lookup"><span data-stu-id="405f8-468">String</span></span>|  
|<span data-ttu-id="405f8-469">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="405f8-469">ORDINAL_POSITION</span></span>|<span data-ttu-id="405f8-470">Int32</span><span class="sxs-lookup"><span data-stu-id="405f8-470">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="405f8-471">Procedure</span><span class="sxs-lookup"><span data-stu-id="405f8-471">Procedures</span></span>  
  
|<span data-ttu-id="405f8-472">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="405f8-472">ColumnName</span></span>|<span data-ttu-id="405f8-473">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="405f8-473">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="405f8-474">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="405f8-474">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="405f8-475">String</span><span class="sxs-lookup"><span data-stu-id="405f8-475">String</span></span>|  
|<span data-ttu-id="405f8-476">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="405f8-476">PROCEDURE_OWNER</span></span>|<span data-ttu-id="405f8-477">String</span><span class="sxs-lookup"><span data-stu-id="405f8-477">String</span></span>|  
|<span data-ttu-id="405f8-478">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="405f8-478">PROCEDURE_NAME</span></span>|<span data-ttu-id="405f8-479">String</span><span class="sxs-lookup"><span data-stu-id="405f8-479">String</span></span>|  
|<span data-ttu-id="405f8-480">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="405f8-480">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="405f8-481">Int16</span><span class="sxs-lookup"><span data-stu-id="405f8-481">Int16</span></span>|  
|<span data-ttu-id="405f8-482">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="405f8-482">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="405f8-483">Int16</span><span class="sxs-lookup"><span data-stu-id="405f8-483">Int16</span></span>|  
|<span data-ttu-id="405f8-484">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="405f8-484">NUM_RESULT_SETS</span></span>|<span data-ttu-id="405f8-485">Int16</span><span class="sxs-lookup"><span data-stu-id="405f8-485">Int16</span></span>|  
|<span data-ttu-id="405f8-486">REMARKS</span><span class="sxs-lookup"><span data-stu-id="405f8-486">REMARKS</span></span>|<span data-ttu-id="405f8-487">String</span><span class="sxs-lookup"><span data-stu-id="405f8-487">String</span></span>|  
|<span data-ttu-id="405f8-488">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="405f8-488">PROCEDURE_TYPE</span></span>|<span data-ttu-id="405f8-489">Int16</span><span class="sxs-lookup"><span data-stu-id="405f8-489">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="405f8-490">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="405f8-490">ProcedureColumns</span></span>  
  
|<span data-ttu-id="405f8-491">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="405f8-491">ColumnName</span></span>|<span data-ttu-id="405f8-492">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="405f8-492">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="405f8-493">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="405f8-493">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="405f8-494">String</span><span class="sxs-lookup"><span data-stu-id="405f8-494">String</span></span>|  
|<span data-ttu-id="405f8-495">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="405f8-495">PROCEDURE_OWNER</span></span>|<span data-ttu-id="405f8-496">String</span><span class="sxs-lookup"><span data-stu-id="405f8-496">String</span></span>|  
|<span data-ttu-id="405f8-497">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="405f8-497">PROCEDURE_NAME</span></span>|<span data-ttu-id="405f8-498">String</span><span class="sxs-lookup"><span data-stu-id="405f8-498">String</span></span>|  
|<span data-ttu-id="405f8-499">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="405f8-499">COLUMN_NAME</span></span>|<span data-ttu-id="405f8-500">String</span><span class="sxs-lookup"><span data-stu-id="405f8-500">String</span></span>|  
|<span data-ttu-id="405f8-501">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="405f8-501">COLUMN_TYPE</span></span>|<span data-ttu-id="405f8-502">Int16</span><span class="sxs-lookup"><span data-stu-id="405f8-502">Int16</span></span>|  
|<span data-ttu-id="405f8-503">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="405f8-503">DATA_TYPE</span></span>|<span data-ttu-id="405f8-504">Int16</span><span class="sxs-lookup"><span data-stu-id="405f8-504">Int16</span></span>|  
|<span data-ttu-id="405f8-505">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="405f8-505">TYPE_NAME</span></span>|<span data-ttu-id="405f8-506">String</span><span class="sxs-lookup"><span data-stu-id="405f8-506">String</span></span>|  
|<span data-ttu-id="405f8-507">PRECISION</span><span class="sxs-lookup"><span data-stu-id="405f8-507">PRECISION</span></span>|<span data-ttu-id="405f8-508">Int32</span><span class="sxs-lookup"><span data-stu-id="405f8-508">Int32</span></span>|  
|<span data-ttu-id="405f8-509">LENGTH</span><span class="sxs-lookup"><span data-stu-id="405f8-509">LENGTH</span></span>|<span data-ttu-id="405f8-510">Int32</span><span class="sxs-lookup"><span data-stu-id="405f8-510">Int32</span></span>|  
|<span data-ttu-id="405f8-511">SCALE</span><span class="sxs-lookup"><span data-stu-id="405f8-511">SCALE</span></span>|<span data-ttu-id="405f8-512">Int16</span><span class="sxs-lookup"><span data-stu-id="405f8-512">Int16</span></span>|  
|<span data-ttu-id="405f8-513">RADIX</span><span class="sxs-lookup"><span data-stu-id="405f8-513">RADIX</span></span>|<span data-ttu-id="405f8-514">Int16</span><span class="sxs-lookup"><span data-stu-id="405f8-514">Int16</span></span>|  
|<span data-ttu-id="405f8-515">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="405f8-515">NULLABLE</span></span>|<span data-ttu-id="405f8-516">Int16</span><span class="sxs-lookup"><span data-stu-id="405f8-516">Int16</span></span>|  
|<span data-ttu-id="405f8-517">REMARKS</span><span class="sxs-lookup"><span data-stu-id="405f8-517">REMARKS</span></span>|<span data-ttu-id="405f8-518">String</span><span class="sxs-lookup"><span data-stu-id="405f8-518">String</span></span>|  
|<span data-ttu-id="405f8-519">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="405f8-519">OVERLOAD</span></span>|<span data-ttu-id="405f8-520">Int32</span><span class="sxs-lookup"><span data-stu-id="405f8-520">Int32</span></span>|  
|<span data-ttu-id="405f8-521">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="405f8-521">ORDINAL_POSITION</span></span>|<span data-ttu-id="405f8-522">Int32</span><span class="sxs-lookup"><span data-stu-id="405f8-522">Int32</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="405f8-523">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="405f8-523">ProcedureParameters</span></span>  
  
|<span data-ttu-id="405f8-524">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="405f8-524">ColumnName</span></span>|<span data-ttu-id="405f8-525">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="405f8-525">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="405f8-526">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="405f8-526">PROCEDURE_CAT</span></span>|<span data-ttu-id="405f8-527">String</span><span class="sxs-lookup"><span data-stu-id="405f8-527">String</span></span>|  
|<span data-ttu-id="405f8-528">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="405f8-528">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="405f8-529">String</span><span class="sxs-lookup"><span data-stu-id="405f8-529">String</span></span>|  
|<span data-ttu-id="405f8-530">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="405f8-530">PROCEDURE_NAME</span></span>|<span data-ttu-id="405f8-531">String</span><span class="sxs-lookup"><span data-stu-id="405f8-531">String</span></span>|  
|<span data-ttu-id="405f8-532">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="405f8-532">COLUMN_NAME</span></span>|<span data-ttu-id="405f8-533">String</span><span class="sxs-lookup"><span data-stu-id="405f8-533">String</span></span>|  
|<span data-ttu-id="405f8-534">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="405f8-534">COLUMN_TYPE</span></span>|<span data-ttu-id="405f8-535">Int16</span><span class="sxs-lookup"><span data-stu-id="405f8-535">Int16</span></span>|  
|<span data-ttu-id="405f8-536">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="405f8-536">DATA_TYPE</span></span>|<span data-ttu-id="405f8-537">Int16</span><span class="sxs-lookup"><span data-stu-id="405f8-537">Int16</span></span>|  
|<span data-ttu-id="405f8-538">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="405f8-538">TYPE_NAME</span></span>|<span data-ttu-id="405f8-539">String</span><span class="sxs-lookup"><span data-stu-id="405f8-539">String</span></span>|  
|<span data-ttu-id="405f8-540">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="405f8-540">COLUMN_SIZE</span></span>|<span data-ttu-id="405f8-541">Int32</span><span class="sxs-lookup"><span data-stu-id="405f8-541">Int32</span></span>|  
|<span data-ttu-id="405f8-542">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="405f8-542">BUFFER_LENGTH</span></span>|<span data-ttu-id="405f8-543">Int32</span><span class="sxs-lookup"><span data-stu-id="405f8-543">Int32</span></span>|  
|<span data-ttu-id="405f8-544">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="405f8-544">DECIMAL_DIGITS</span></span>|<span data-ttu-id="405f8-545">Int16</span><span class="sxs-lookup"><span data-stu-id="405f8-545">Int16</span></span>|  
|<span data-ttu-id="405f8-546">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="405f8-546">NUM_PREC_RADIX</span></span>|<span data-ttu-id="405f8-547">Int16</span><span class="sxs-lookup"><span data-stu-id="405f8-547">Int16</span></span>|  
|<span data-ttu-id="405f8-548">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="405f8-548">NULLABLE</span></span>|<span data-ttu-id="405f8-549">Int16</span><span class="sxs-lookup"><span data-stu-id="405f8-549">Int16</span></span>|  
|<span data-ttu-id="405f8-550">REMARKS</span><span class="sxs-lookup"><span data-stu-id="405f8-550">REMARKS</span></span>|<span data-ttu-id="405f8-551">String</span><span class="sxs-lookup"><span data-stu-id="405f8-551">String</span></span>|  
|<span data-ttu-id="405f8-552">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="405f8-552">COLUMN_DEF</span></span>|<span data-ttu-id="405f8-553">String</span><span class="sxs-lookup"><span data-stu-id="405f8-553">String</span></span>|  
|<span data-ttu-id="405f8-554">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="405f8-554">SQL_DATA_TYPE</span></span>|<span data-ttu-id="405f8-555">Int16</span><span class="sxs-lookup"><span data-stu-id="405f8-555">Int16</span></span>|  
|<span data-ttu-id="405f8-556">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="405f8-556">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="405f8-557">Int16</span><span class="sxs-lookup"><span data-stu-id="405f8-557">Int16</span></span>|  
|<span data-ttu-id="405f8-558">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="405f8-558">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="405f8-559">Int32</span><span class="sxs-lookup"><span data-stu-id="405f8-559">Int32</span></span>|  
|<span data-ttu-id="405f8-560">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="405f8-560">ORDINAL_POSITION</span></span>|<span data-ttu-id="405f8-561">Int32</span><span class="sxs-lookup"><span data-stu-id="405f8-561">Int32</span></span>|  
|<span data-ttu-id="405f8-562">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="405f8-562">IS_NULLABLE</span></span>|<span data-ttu-id="405f8-563">Stringa</span><span class="sxs-lookup"><span data-stu-id="405f8-563">String</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="405f8-564">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="405f8-564">See Also</span></span>  
 [<span data-ttu-id="405f8-565">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="405f8-565">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
