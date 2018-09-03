---
title: Raccolte di schemi ODBC
ms.date: 03/30/2017
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
ms.openlocfilehash: bdedbb11960f02b99dcca6388abf663635238f74
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2018
ms.locfileid: "43479980"
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="102a8-102">Raccolte di schemi ODBC</span><span class="sxs-lookup"><span data-stu-id="102a8-102">ODBC Schema Collections</span></span>
<span data-ttu-id="102a8-103">Contenuto della sezione viene descritto il supporto delle raccolte di schemi per driver ODBC per Microsoft SQL Server, Oracle e Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="102a8-103">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="102a8-104">Driver ODBC di Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="102a8-104">Microsoft SQL Server ODBC Driver</span></span>  
 <span data-ttu-id="102a8-105">Il Driver ODBC di Microsoft SQL Server supporta le seguenti raccolte di schemi specifici oltre alle raccolte di schemi comuni:</span><span class="sxs-lookup"><span data-stu-id="102a8-105">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="102a8-106">Tabelle</span><span class="sxs-lookup"><span data-stu-id="102a8-106">Tables</span></span>  
  
-   <span data-ttu-id="102a8-107">Indexes</span><span class="sxs-lookup"><span data-stu-id="102a8-107">Indexes</span></span>  
  
-   <span data-ttu-id="102a8-108">Colonne</span><span class="sxs-lookup"><span data-stu-id="102a8-108">Columns</span></span>  
  
-   <span data-ttu-id="102a8-109">Procedure</span><span class="sxs-lookup"><span data-stu-id="102a8-109">Procedures</span></span>  
  
-   <span data-ttu-id="102a8-110">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="102a8-110">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="102a8-111">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="102a8-111">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="102a8-112">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="102a8-112">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="102a8-113">Tables e Views</span><span class="sxs-lookup"><span data-stu-id="102a8-113">Tables and Views</span></span>  
  
|<span data-ttu-id="102a8-114">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="102a8-114">ColumnName</span></span>|<span data-ttu-id="102a8-115">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="102a8-115">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="102a8-116">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="102a8-116">TABLE_CAT</span></span>|<span data-ttu-id="102a8-117">String</span><span class="sxs-lookup"><span data-stu-id="102a8-117">String</span></span>|  
|<span data-ttu-id="102a8-118">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="102a8-118">TABLE_SCHEM</span></span>|<span data-ttu-id="102a8-119">String</span><span class="sxs-lookup"><span data-stu-id="102a8-119">String</span></span>|  
|<span data-ttu-id="102a8-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="102a8-120">TABLE_NAME</span></span>|<span data-ttu-id="102a8-121">String</span><span class="sxs-lookup"><span data-stu-id="102a8-121">String</span></span>|  
|<span data-ttu-id="102a8-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="102a8-122">TABLE_TYPE</span></span>|<span data-ttu-id="102a8-123">String</span><span class="sxs-lookup"><span data-stu-id="102a8-123">String</span></span>|  
|<span data-ttu-id="102a8-124">REMARKS</span><span class="sxs-lookup"><span data-stu-id="102a8-124">REMARKS</span></span>|<span data-ttu-id="102a8-125">String</span><span class="sxs-lookup"><span data-stu-id="102a8-125">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="102a8-126">Indexes</span><span class="sxs-lookup"><span data-stu-id="102a8-126">Indexes</span></span>  
  
|<span data-ttu-id="102a8-127">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="102a8-127">ColumnName</span></span>|<span data-ttu-id="102a8-128">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="102a8-128">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="102a8-129">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="102a8-129">TABLE_CAT</span></span>|<span data-ttu-id="102a8-130">String</span><span class="sxs-lookup"><span data-stu-id="102a8-130">String</span></span>|  
|<span data-ttu-id="102a8-131">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="102a8-131">TABLE_SCHEM</span></span>|<span data-ttu-id="102a8-132">String</span><span class="sxs-lookup"><span data-stu-id="102a8-132">String</span></span>|  
|<span data-ttu-id="102a8-133">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="102a8-133">TABLE_NAME</span></span>|<span data-ttu-id="102a8-134">String</span><span class="sxs-lookup"><span data-stu-id="102a8-134">String</span></span>|  
|<span data-ttu-id="102a8-135">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="102a8-135">NON_UNIQUE</span></span>|<span data-ttu-id="102a8-136">Int16</span><span class="sxs-lookup"><span data-stu-id="102a8-136">Int16</span></span>|  
|<span data-ttu-id="102a8-137">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="102a8-137">INDEX_QUALIFIER</span></span>|<span data-ttu-id="102a8-138">String</span><span class="sxs-lookup"><span data-stu-id="102a8-138">String</span></span>|  
|<span data-ttu-id="102a8-139">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="102a8-139">INDEX_NAME</span></span>|<span data-ttu-id="102a8-140">String</span><span class="sxs-lookup"><span data-stu-id="102a8-140">String</span></span>|  
|<span data-ttu-id="102a8-141">TYPE</span><span class="sxs-lookup"><span data-stu-id="102a8-141">TYPE</span></span>|<span data-ttu-id="102a8-142">Int16</span><span class="sxs-lookup"><span data-stu-id="102a8-142">Int16</span></span>|  
|<span data-ttu-id="102a8-143">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="102a8-143">ORDINAL_POSITION</span></span>|<span data-ttu-id="102a8-144">Int16</span><span class="sxs-lookup"><span data-stu-id="102a8-144">Int16</span></span>|  
|<span data-ttu-id="102a8-145">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="102a8-145">COLUMN_NAME</span></span>|<span data-ttu-id="102a8-146">String</span><span class="sxs-lookup"><span data-stu-id="102a8-146">String</span></span>|  
|<span data-ttu-id="102a8-147">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="102a8-147">ASC_OR_DESC</span></span>|<span data-ttu-id="102a8-148">String</span><span class="sxs-lookup"><span data-stu-id="102a8-148">String</span></span>|  
|<span data-ttu-id="102a8-149">CARDINATLITY</span><span class="sxs-lookup"><span data-stu-id="102a8-149">CARDINATLITY</span></span>|<span data-ttu-id="102a8-150">Int32</span><span class="sxs-lookup"><span data-stu-id="102a8-150">Int32</span></span>|  
|<span data-ttu-id="102a8-151">PAGES</span><span class="sxs-lookup"><span data-stu-id="102a8-151">PAGES</span></span>|<span data-ttu-id="102a8-152">Int32</span><span class="sxs-lookup"><span data-stu-id="102a8-152">Int32</span></span>|  
|<span data-ttu-id="102a8-153">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="102a8-153">FILTER_CONDITION</span></span>|<span data-ttu-id="102a8-154">String</span><span class="sxs-lookup"><span data-stu-id="102a8-154">String</span></span>|  
|<span data-ttu-id="102a8-155">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="102a8-155">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="102a8-156">String</span><span class="sxs-lookup"><span data-stu-id="102a8-156">String</span></span>|  
|<span data-ttu-id="102a8-157">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="102a8-157">SS_DATA_TYPE</span></span>|<span data-ttu-id="102a8-158">Byte</span><span class="sxs-lookup"><span data-stu-id="102a8-158">Byte</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="102a8-159">Colonne</span><span class="sxs-lookup"><span data-stu-id="102a8-159">Columns</span></span>  
  
|<span data-ttu-id="102a8-160">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="102a8-160">ColumnName</span></span>|<span data-ttu-id="102a8-161">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="102a8-161">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="102a8-162">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="102a8-162">TABLE_CAT</span></span>|<span data-ttu-id="102a8-163">String</span><span class="sxs-lookup"><span data-stu-id="102a8-163">String</span></span>|  
|<span data-ttu-id="102a8-164">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="102a8-164">TABLE_SCHEM</span></span>|<span data-ttu-id="102a8-165">String</span><span class="sxs-lookup"><span data-stu-id="102a8-165">String</span></span>|  
|<span data-ttu-id="102a8-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="102a8-166">TABLE_NAME</span></span>|<span data-ttu-id="102a8-167">String</span><span class="sxs-lookup"><span data-stu-id="102a8-167">String</span></span>|  
|<span data-ttu-id="102a8-168">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="102a8-168">COLUMN_NAME</span></span>|<span data-ttu-id="102a8-169">String</span><span class="sxs-lookup"><span data-stu-id="102a8-169">String</span></span>|  
|<span data-ttu-id="102a8-170">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="102a8-170">DATA_TYPE</span></span>|<span data-ttu-id="102a8-171">Int16</span><span class="sxs-lookup"><span data-stu-id="102a8-171">Int16</span></span>|  
|<span data-ttu-id="102a8-172">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="102a8-172">TYPE_NAME</span></span>|<span data-ttu-id="102a8-173">String</span><span class="sxs-lookup"><span data-stu-id="102a8-173">String</span></span>|  
|<span data-ttu-id="102a8-174">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="102a8-174">COLUMN_SIZE</span></span>|<span data-ttu-id="102a8-175">Int32</span><span class="sxs-lookup"><span data-stu-id="102a8-175">Int32</span></span>|  
|<span data-ttu-id="102a8-176">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="102a8-176">BUFFER_LENGTH</span></span>|<span data-ttu-id="102a8-177">Int32</span><span class="sxs-lookup"><span data-stu-id="102a8-177">Int32</span></span>|  
|<span data-ttu-id="102a8-178">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="102a8-178">DECIMAL_DIGITS</span></span>|<span data-ttu-id="102a8-179">Int16</span><span class="sxs-lookup"><span data-stu-id="102a8-179">Int16</span></span>|  
|<span data-ttu-id="102a8-180">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="102a8-180">NUM_PREC_RADIX</span></span>|<span data-ttu-id="102a8-181">Int16</span><span class="sxs-lookup"><span data-stu-id="102a8-181">Int16</span></span>|  
|<span data-ttu-id="102a8-182">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="102a8-182">NULLABLE</span></span>|<span data-ttu-id="102a8-183">Int16</span><span class="sxs-lookup"><span data-stu-id="102a8-183">Int16</span></span>|  
|<span data-ttu-id="102a8-184">REMARKS</span><span class="sxs-lookup"><span data-stu-id="102a8-184">REMARKS</span></span>|<span data-ttu-id="102a8-185">String</span><span class="sxs-lookup"><span data-stu-id="102a8-185">String</span></span>|  
|<span data-ttu-id="102a8-186">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="102a8-186">COLUMN_DEF</span></span>|<span data-ttu-id="102a8-187">String</span><span class="sxs-lookup"><span data-stu-id="102a8-187">String</span></span>|  
|<span data-ttu-id="102a8-188">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="102a8-188">SQL_DATA_TYPE</span></span>|<span data-ttu-id="102a8-189">Int16</span><span class="sxs-lookup"><span data-stu-id="102a8-189">Int16</span></span>|  
|<span data-ttu-id="102a8-190">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="102a8-190">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="102a8-191">Int16</span><span class="sxs-lookup"><span data-stu-id="102a8-191">Int16</span></span>|  
|<span data-ttu-id="102a8-192">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="102a8-192">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="102a8-193">Int32</span><span class="sxs-lookup"><span data-stu-id="102a8-193">Int32</span></span>|  
|<span data-ttu-id="102a8-194">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="102a8-194">ORDINAL_POSITION</span></span>|<span data-ttu-id="102a8-195">Int32</span><span class="sxs-lookup"><span data-stu-id="102a8-195">Int32</span></span>|  
|<span data-ttu-id="102a8-196">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="102a8-196">IS_NULLABLE</span></span>|<span data-ttu-id="102a8-197">String</span><span class="sxs-lookup"><span data-stu-id="102a8-197">String</span></span>|  
|<span data-ttu-id="102a8-198">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="102a8-198">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="102a8-199">String</span><span class="sxs-lookup"><span data-stu-id="102a8-199">String</span></span>|  
|<span data-ttu-id="102a8-200">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="102a8-200">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="102a8-201">String</span><span class="sxs-lookup"><span data-stu-id="102a8-201">String</span></span>|  
|<span data-ttu-id="102a8-202">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="102a8-202">SS_DATA_TYPE</span></span>|<span data-ttu-id="102a8-203">Byte</span><span class="sxs-lookup"><span data-stu-id="102a8-203">Byte</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="102a8-204">Procedure</span><span class="sxs-lookup"><span data-stu-id="102a8-204">Procedures</span></span>  
  
|<span data-ttu-id="102a8-205">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="102a8-205">ColumnName</span></span>|<span data-ttu-id="102a8-206">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="102a8-206">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="102a8-207">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="102a8-207">PROCEDURE_CAT</span></span>|<span data-ttu-id="102a8-208">String</span><span class="sxs-lookup"><span data-stu-id="102a8-208">String</span></span>|  
|<span data-ttu-id="102a8-209">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="102a8-209">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="102a8-210">String</span><span class="sxs-lookup"><span data-stu-id="102a8-210">String</span></span>|  
|<span data-ttu-id="102a8-211">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="102a8-211">PROCEDURE_NAME</span></span>|<span data-ttu-id="102a8-212">String</span><span class="sxs-lookup"><span data-stu-id="102a8-212">String</span></span>|  
|<span data-ttu-id="102a8-213">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="102a8-213">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="102a8-214">Int32</span><span class="sxs-lookup"><span data-stu-id="102a8-214">Int32</span></span>|  
|<span data-ttu-id="102a8-215">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="102a8-215">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="102a8-216">Int32</span><span class="sxs-lookup"><span data-stu-id="102a8-216">Int32</span></span>|  
|<span data-ttu-id="102a8-217">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="102a8-217">NUM_RESULT_SETS</span></span>|<span data-ttu-id="102a8-218">Int32</span><span class="sxs-lookup"><span data-stu-id="102a8-218">Int32</span></span>|  
|<span data-ttu-id="102a8-219">REMARKS</span><span class="sxs-lookup"><span data-stu-id="102a8-219">REMARKS</span></span>|<span data-ttu-id="102a8-220">String</span><span class="sxs-lookup"><span data-stu-id="102a8-220">String</span></span>|  
|<span data-ttu-id="102a8-221">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="102a8-221">PROCEDURE_TYPE</span></span>|<span data-ttu-id="102a8-222">Int16</span><span class="sxs-lookup"><span data-stu-id="102a8-222">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="102a8-223">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="102a8-223">ProcedureColumns</span></span>  
  
|<span data-ttu-id="102a8-224">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="102a8-224">ColumnName</span></span>|<span data-ttu-id="102a8-225">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="102a8-225">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="102a8-226">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="102a8-226">PROCEDURE_CAT</span></span>|<span data-ttu-id="102a8-227">String</span><span class="sxs-lookup"><span data-stu-id="102a8-227">String</span></span>|  
|<span data-ttu-id="102a8-228">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="102a8-228">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="102a8-229">String</span><span class="sxs-lookup"><span data-stu-id="102a8-229">String</span></span>|  
|<span data-ttu-id="102a8-230">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="102a8-230">PROCEDURE_NAME</span></span>|<span data-ttu-id="102a8-231">String</span><span class="sxs-lookup"><span data-stu-id="102a8-231">String</span></span>|  
|<span data-ttu-id="102a8-232">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="102a8-232">COLUMN_NAME</span></span>|<span data-ttu-id="102a8-233">String</span><span class="sxs-lookup"><span data-stu-id="102a8-233">String</span></span>|  
|<span data-ttu-id="102a8-234">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="102a8-234">COLUMN_TYPE</span></span>|<span data-ttu-id="102a8-235">Int16</span><span class="sxs-lookup"><span data-stu-id="102a8-235">Int16</span></span>|  
|<span data-ttu-id="102a8-236">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="102a8-236">DATA_TYPE</span></span>|<span data-ttu-id="102a8-237">Int16</span><span class="sxs-lookup"><span data-stu-id="102a8-237">Int16</span></span>|  
|<span data-ttu-id="102a8-238">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="102a8-238">TYPE_NAME</span></span>|<span data-ttu-id="102a8-239">String</span><span class="sxs-lookup"><span data-stu-id="102a8-239">String</span></span>|  
|<span data-ttu-id="102a8-240">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="102a8-240">COLUMN_SIZE</span></span>|<span data-ttu-id="102a8-241">Int32</span><span class="sxs-lookup"><span data-stu-id="102a8-241">Int32</span></span>|  
|<span data-ttu-id="102a8-242">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="102a8-242">BUFFER_LENGTH</span></span>|<span data-ttu-id="102a8-243">Int32</span><span class="sxs-lookup"><span data-stu-id="102a8-243">Int32</span></span>|  
|<span data-ttu-id="102a8-244">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="102a8-244">DECIMAL_DIGITS</span></span>|<span data-ttu-id="102a8-245">Int16</span><span class="sxs-lookup"><span data-stu-id="102a8-245">Int16</span></span>|  
|<span data-ttu-id="102a8-246">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="102a8-246">NUM_PREC_RADIX</span></span>|<span data-ttu-id="102a8-247">Int16</span><span class="sxs-lookup"><span data-stu-id="102a8-247">Int16</span></span>|  
|<span data-ttu-id="102a8-248">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="102a8-248">NULLABLE</span></span>|<span data-ttu-id="102a8-249">Int16</span><span class="sxs-lookup"><span data-stu-id="102a8-249">Int16</span></span>|  
|<span data-ttu-id="102a8-250">REMARKS</span><span class="sxs-lookup"><span data-stu-id="102a8-250">REMARKS</span></span>|<span data-ttu-id="102a8-251">String</span><span class="sxs-lookup"><span data-stu-id="102a8-251">String</span></span>|  
|<span data-ttu-id="102a8-252">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="102a8-252">COLUMN_DEF</span></span>|<span data-ttu-id="102a8-253">String</span><span class="sxs-lookup"><span data-stu-id="102a8-253">String</span></span>|  
|<span data-ttu-id="102a8-254">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="102a8-254">SQL_DATA_TYPE</span></span>|<span data-ttu-id="102a8-255">Int16</span><span class="sxs-lookup"><span data-stu-id="102a8-255">Int16</span></span>|  
|<span data-ttu-id="102a8-256">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="102a8-256">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="102a8-257">Int16</span><span class="sxs-lookup"><span data-stu-id="102a8-257">Int16</span></span>|  
|<span data-ttu-id="102a8-258">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="102a8-258">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="102a8-259">Int32</span><span class="sxs-lookup"><span data-stu-id="102a8-259">Int32</span></span>|  
|<span data-ttu-id="102a8-260">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="102a8-260">ORDINAL_POSITION</span></span>|<span data-ttu-id="102a8-261">Int32</span><span class="sxs-lookup"><span data-stu-id="102a8-261">Int32</span></span>|  
|<span data-ttu-id="102a8-262">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="102a8-262">IS_NULLABLE</span></span>|<span data-ttu-id="102a8-263">String</span><span class="sxs-lookup"><span data-stu-id="102a8-263">String</span></span>|  
|<span data-ttu-id="102a8-264">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="102a8-264">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="102a8-265">String</span><span class="sxs-lookup"><span data-stu-id="102a8-265">String</span></span>|  
|<span data-ttu-id="102a8-266">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="102a8-266">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="102a8-267">String</span><span class="sxs-lookup"><span data-stu-id="102a8-267">String</span></span>|  
|<span data-ttu-id="102a8-268">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="102a8-268">SS_DATA_TYPE</span></span>|<span data-ttu-id="102a8-269">Byte</span><span class="sxs-lookup"><span data-stu-id="102a8-269">Byte</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="102a8-270">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="102a8-270">ProcedureParameters</span></span>  
  
|<span data-ttu-id="102a8-271">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="102a8-271">ColumnName</span></span>|<span data-ttu-id="102a8-272">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="102a8-272">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="102a8-273">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="102a8-273">PROCEDURE_CAT</span></span>|<span data-ttu-id="102a8-274">String</span><span class="sxs-lookup"><span data-stu-id="102a8-274">String</span></span>|  
|<span data-ttu-id="102a8-275">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="102a8-275">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="102a8-276">String</span><span class="sxs-lookup"><span data-stu-id="102a8-276">String</span></span>|  
|<span data-ttu-id="102a8-277">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="102a8-277">PROCEDURE_NAME</span></span>|<span data-ttu-id="102a8-278">String</span><span class="sxs-lookup"><span data-stu-id="102a8-278">String</span></span>|  
|<span data-ttu-id="102a8-279">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="102a8-279">COLUMN_NAME</span></span>|<span data-ttu-id="102a8-280">String</span><span class="sxs-lookup"><span data-stu-id="102a8-280">String</span></span>|  
|<span data-ttu-id="102a8-281">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="102a8-281">COLUMN_TYPE</span></span>|<span data-ttu-id="102a8-282">Int16</span><span class="sxs-lookup"><span data-stu-id="102a8-282">Int16</span></span>|  
|<span data-ttu-id="102a8-283">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="102a8-283">DATA_TYPE</span></span>|<span data-ttu-id="102a8-284">Int16</span><span class="sxs-lookup"><span data-stu-id="102a8-284">Int16</span></span>|  
|<span data-ttu-id="102a8-285">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="102a8-285">TYPE_NAME</span></span>|<span data-ttu-id="102a8-286">String</span><span class="sxs-lookup"><span data-stu-id="102a8-286">String</span></span>|  
|<span data-ttu-id="102a8-287">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="102a8-287">COLUMN_SIZE</span></span>|<span data-ttu-id="102a8-288">Int32</span><span class="sxs-lookup"><span data-stu-id="102a8-288">Int32</span></span>|  
|<span data-ttu-id="102a8-289">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="102a8-289">BUFFER_LENGTH</span></span>|<span data-ttu-id="102a8-290">Int32</span><span class="sxs-lookup"><span data-stu-id="102a8-290">Int32</span></span>|  
|<span data-ttu-id="102a8-291">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="102a8-291">DECIMAL_DIGITS</span></span>|<span data-ttu-id="102a8-292">Int16</span><span class="sxs-lookup"><span data-stu-id="102a8-292">Int16</span></span>|  
|<span data-ttu-id="102a8-293">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="102a8-293">NUM_PREC_RADIX</span></span>|<span data-ttu-id="102a8-294">Int16</span><span class="sxs-lookup"><span data-stu-id="102a8-294">Int16</span></span>|  
|<span data-ttu-id="102a8-295">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="102a8-295">NULLABLE</span></span>|<span data-ttu-id="102a8-296">Int16</span><span class="sxs-lookup"><span data-stu-id="102a8-296">Int16</span></span>|  
|<span data-ttu-id="102a8-297">REMARKS</span><span class="sxs-lookup"><span data-stu-id="102a8-297">REMARKS</span></span>|<span data-ttu-id="102a8-298">String</span><span class="sxs-lookup"><span data-stu-id="102a8-298">String</span></span>|  
|<span data-ttu-id="102a8-299">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="102a8-299">COLUMN_DEF</span></span>|<span data-ttu-id="102a8-300">String</span><span class="sxs-lookup"><span data-stu-id="102a8-300">String</span></span>|  
|<span data-ttu-id="102a8-301">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="102a8-301">SQL_DATA_TYPE</span></span>|<span data-ttu-id="102a8-302">Int16</span><span class="sxs-lookup"><span data-stu-id="102a8-302">Int16</span></span>|  
|<span data-ttu-id="102a8-303">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="102a8-303">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="102a8-304">Int16</span><span class="sxs-lookup"><span data-stu-id="102a8-304">Int16</span></span>|  
|<span data-ttu-id="102a8-305">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="102a8-305">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="102a8-306">Int32</span><span class="sxs-lookup"><span data-stu-id="102a8-306">Int32</span></span>|  
|<span data-ttu-id="102a8-307">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="102a8-307">ORDINAL_POSITION</span></span>|<span data-ttu-id="102a8-308">Int32</span><span class="sxs-lookup"><span data-stu-id="102a8-308">Int32</span></span>|  
|<span data-ttu-id="102a8-309">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="102a8-309">IS_NULLABLE</span></span>|<span data-ttu-id="102a8-310">String</span><span class="sxs-lookup"><span data-stu-id="102a8-310">String</span></span>|  
|<span data-ttu-id="102a8-311">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="102a8-311">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="102a8-312">String</span><span class="sxs-lookup"><span data-stu-id="102a8-312">String</span></span>|  
|<span data-ttu-id="102a8-313">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="102a8-313">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="102a8-314">String</span><span class="sxs-lookup"><span data-stu-id="102a8-314">String</span></span>|  
|<span data-ttu-id="102a8-315">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="102a8-315">SS_DATA_TYPE</span></span>|<span data-ttu-id="102a8-316">Byte</span><span class="sxs-lookup"><span data-stu-id="102a8-316">Byte</span></span>|  
  
## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="102a8-317">Driver Microsoft ODBC per Oracle</span><span class="sxs-lookup"><span data-stu-id="102a8-317">Microsoft Oracle ODBC Driver</span></span>  
 <span data-ttu-id="102a8-318">Il Driver ODBC di Microsoft SQL Server Oracle supporta le seguenti raccolte di schemi specifici oltre alle raccolte di schemi comuni:</span><span class="sxs-lookup"><span data-stu-id="102a8-318">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="102a8-319">Tabelle</span><span class="sxs-lookup"><span data-stu-id="102a8-319">Tables</span></span>  
  
-   <span data-ttu-id="102a8-320">Colonne</span><span class="sxs-lookup"><span data-stu-id="102a8-320">Columns</span></span>  
  
-   <span data-ttu-id="102a8-321">Procedure</span><span class="sxs-lookup"><span data-stu-id="102a8-321">Procedures</span></span>  
  
-   <span data-ttu-id="102a8-322">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="102a8-322">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="102a8-323">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="102a8-323">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="102a8-324">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="102a8-324">Views</span></span>  
  
-   <span data-ttu-id="102a8-325">Indexes</span><span class="sxs-lookup"><span data-stu-id="102a8-325">Indexes</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="102a8-326">Tables e Views</span><span class="sxs-lookup"><span data-stu-id="102a8-326">Tables and Views</span></span>  
  
|<span data-ttu-id="102a8-327">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="102a8-327">ColumnName</span></span>|<span data-ttu-id="102a8-328">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="102a8-328">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="102a8-329">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="102a8-329">TABLE_QUALIFIER</span></span>|<span data-ttu-id="102a8-330">String</span><span class="sxs-lookup"><span data-stu-id="102a8-330">String</span></span>|  
|<span data-ttu-id="102a8-331">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="102a8-331">TABLE_OWNER</span></span>|<span data-ttu-id="102a8-332">String</span><span class="sxs-lookup"><span data-stu-id="102a8-332">String</span></span>|  
|<span data-ttu-id="102a8-333">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="102a8-333">TABLE_NAME</span></span>|<span data-ttu-id="102a8-334">String</span><span class="sxs-lookup"><span data-stu-id="102a8-334">String</span></span>|  
|<span data-ttu-id="102a8-335">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="102a8-335">TABLE_TYPE</span></span>|<span data-ttu-id="102a8-336">String</span><span class="sxs-lookup"><span data-stu-id="102a8-336">String</span></span>|  
|<span data-ttu-id="102a8-337">REMARKS</span><span class="sxs-lookup"><span data-stu-id="102a8-337">REMARKS</span></span>|<span data-ttu-id="102a8-338">String</span><span class="sxs-lookup"><span data-stu-id="102a8-338">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="102a8-339">Colonne</span><span class="sxs-lookup"><span data-stu-id="102a8-339">Columns</span></span>  
  
|<span data-ttu-id="102a8-340">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="102a8-340">ColumnName</span></span>|<span data-ttu-id="102a8-341">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="102a8-341">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="102a8-342">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="102a8-342">TABLE_QUALIFIER</span></span>|<span data-ttu-id="102a8-343">String</span><span class="sxs-lookup"><span data-stu-id="102a8-343">String</span></span>|  
|<span data-ttu-id="102a8-344">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="102a8-344">TABLE_OWNER</span></span>|<span data-ttu-id="102a8-345">String</span><span class="sxs-lookup"><span data-stu-id="102a8-345">String</span></span>|  
|<span data-ttu-id="102a8-346">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="102a8-346">TABLE_NAME</span></span>|<span data-ttu-id="102a8-347">String</span><span class="sxs-lookup"><span data-stu-id="102a8-347">String</span></span>|  
|<span data-ttu-id="102a8-348">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="102a8-348">COLUMN_NAME</span></span>|<span data-ttu-id="102a8-349">String</span><span class="sxs-lookup"><span data-stu-id="102a8-349">String</span></span>|  
|<span data-ttu-id="102a8-350">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="102a8-350">DATA_TYPE</span></span>|<span data-ttu-id="102a8-351">Int16</span><span class="sxs-lookup"><span data-stu-id="102a8-351">Int16</span></span>|  
|<span data-ttu-id="102a8-352">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="102a8-352">TYPE_NAME</span></span>|<span data-ttu-id="102a8-353">String</span><span class="sxs-lookup"><span data-stu-id="102a8-353">String</span></span>|  
|<span data-ttu-id="102a8-354">PRECISION</span><span class="sxs-lookup"><span data-stu-id="102a8-354">PRECISION</span></span>|<span data-ttu-id="102a8-355">Int32</span><span class="sxs-lookup"><span data-stu-id="102a8-355">Int32</span></span>|  
|<span data-ttu-id="102a8-356">LENGTH</span><span class="sxs-lookup"><span data-stu-id="102a8-356">LENGTH</span></span>|<span data-ttu-id="102a8-357">Int32</span><span class="sxs-lookup"><span data-stu-id="102a8-357">Int32</span></span>|  
|<span data-ttu-id="102a8-358">SCALE</span><span class="sxs-lookup"><span data-stu-id="102a8-358">SCALE</span></span>|<span data-ttu-id="102a8-359">Int16</span><span class="sxs-lookup"><span data-stu-id="102a8-359">Int16</span></span>|  
|<span data-ttu-id="102a8-360">RADIX</span><span class="sxs-lookup"><span data-stu-id="102a8-360">RADIX</span></span>|<span data-ttu-id="102a8-361">Int16</span><span class="sxs-lookup"><span data-stu-id="102a8-361">Int16</span></span>|  
|<span data-ttu-id="102a8-362">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="102a8-362">NULLABLE</span></span>|<span data-ttu-id="102a8-363">Int16</span><span class="sxs-lookup"><span data-stu-id="102a8-363">Int16</span></span>|  
|<span data-ttu-id="102a8-364">REMARKS</span><span class="sxs-lookup"><span data-stu-id="102a8-364">REMARKS</span></span>|<span data-ttu-id="102a8-365">String</span><span class="sxs-lookup"><span data-stu-id="102a8-365">String</span></span>|  
|<span data-ttu-id="102a8-366">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="102a8-366">ORDINAL_POSITION</span></span>|<span data-ttu-id="102a8-367">Int32</span><span class="sxs-lookup"><span data-stu-id="102a8-367">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="102a8-368">Procedure</span><span class="sxs-lookup"><span data-stu-id="102a8-368">Procedures</span></span>  
  
|<span data-ttu-id="102a8-369">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="102a8-369">ColumnName</span></span>|<span data-ttu-id="102a8-370">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="102a8-370">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="102a8-371">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="102a8-371">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="102a8-372">String</span><span class="sxs-lookup"><span data-stu-id="102a8-372">String</span></span>|  
|<span data-ttu-id="102a8-373">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="102a8-373">PROCEDURE_OWNER</span></span>|<span data-ttu-id="102a8-374">String</span><span class="sxs-lookup"><span data-stu-id="102a8-374">String</span></span>|  
|<span data-ttu-id="102a8-375">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="102a8-375">PROCEDURE_NAME</span></span>|<span data-ttu-id="102a8-376">String</span><span class="sxs-lookup"><span data-stu-id="102a8-376">String</span></span>|  
|<span data-ttu-id="102a8-377">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="102a8-377">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="102a8-378">Int16</span><span class="sxs-lookup"><span data-stu-id="102a8-378">Int16</span></span>|  
|<span data-ttu-id="102a8-379">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="102a8-379">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="102a8-380">Int16</span><span class="sxs-lookup"><span data-stu-id="102a8-380">Int16</span></span>|  
|<span data-ttu-id="102a8-381">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="102a8-381">NUM_RESULT_SETS</span></span>|<span data-ttu-id="102a8-382">Int16</span><span class="sxs-lookup"><span data-stu-id="102a8-382">Int16</span></span>|  
|<span data-ttu-id="102a8-383">REMARKS</span><span class="sxs-lookup"><span data-stu-id="102a8-383">REMARKS</span></span>|<span data-ttu-id="102a8-384">String</span><span class="sxs-lookup"><span data-stu-id="102a8-384">String</span></span>|  
|<span data-ttu-id="102a8-385">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="102a8-385">PROCEDURE_TYPE</span></span>|<span data-ttu-id="102a8-386">Int16</span><span class="sxs-lookup"><span data-stu-id="102a8-386">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="102a8-387">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="102a8-387">ProcedureColumns</span></span>  
  
|<span data-ttu-id="102a8-388">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="102a8-388">ColumnName</span></span>|<span data-ttu-id="102a8-389">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="102a8-389">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="102a8-390">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="102a8-390">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="102a8-391">String</span><span class="sxs-lookup"><span data-stu-id="102a8-391">String</span></span>|  
|<span data-ttu-id="102a8-392">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="102a8-392">PROCEDURE_OWNER</span></span>|<span data-ttu-id="102a8-393">String</span><span class="sxs-lookup"><span data-stu-id="102a8-393">String</span></span>|  
|<span data-ttu-id="102a8-394">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="102a8-394">PROCEDURE_NAME</span></span>|<span data-ttu-id="102a8-395">String</span><span class="sxs-lookup"><span data-stu-id="102a8-395">String</span></span>|  
|<span data-ttu-id="102a8-396">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="102a8-396">COLUMN_NAME</span></span>|<span data-ttu-id="102a8-397">String</span><span class="sxs-lookup"><span data-stu-id="102a8-397">String</span></span>|  
|<span data-ttu-id="102a8-398">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="102a8-398">COLUMN_TYPE</span></span>|<span data-ttu-id="102a8-399">Int16</span><span class="sxs-lookup"><span data-stu-id="102a8-399">Int16</span></span>|  
|<span data-ttu-id="102a8-400">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="102a8-400">DATA_TYPE</span></span>|<span data-ttu-id="102a8-401">Int16</span><span class="sxs-lookup"><span data-stu-id="102a8-401">Int16</span></span>|  
|<span data-ttu-id="102a8-402">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="102a8-402">TYPE_NAME</span></span>|<span data-ttu-id="102a8-403">String</span><span class="sxs-lookup"><span data-stu-id="102a8-403">String</span></span>|  
|<span data-ttu-id="102a8-404">PRECISION</span><span class="sxs-lookup"><span data-stu-id="102a8-404">PRECISION</span></span>|<span data-ttu-id="102a8-405">Int32</span><span class="sxs-lookup"><span data-stu-id="102a8-405">Int32</span></span>|  
|<span data-ttu-id="102a8-406">LENGTH</span><span class="sxs-lookup"><span data-stu-id="102a8-406">LENGTH</span></span>|<span data-ttu-id="102a8-407">Int32</span><span class="sxs-lookup"><span data-stu-id="102a8-407">Int32</span></span>|  
|<span data-ttu-id="102a8-408">SCALE</span><span class="sxs-lookup"><span data-stu-id="102a8-408">SCALE</span></span>|<span data-ttu-id="102a8-409">Int16</span><span class="sxs-lookup"><span data-stu-id="102a8-409">Int16</span></span>|  
|<span data-ttu-id="102a8-410">RADIX</span><span class="sxs-lookup"><span data-stu-id="102a8-410">RADIX</span></span>|<span data-ttu-id="102a8-411">Int16</span><span class="sxs-lookup"><span data-stu-id="102a8-411">Int16</span></span>|  
|<span data-ttu-id="102a8-412">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="102a8-412">NULLABLE</span></span>|<span data-ttu-id="102a8-413">Int16</span><span class="sxs-lookup"><span data-stu-id="102a8-413">Int16</span></span>|  
|<span data-ttu-id="102a8-414">REMARKS</span><span class="sxs-lookup"><span data-stu-id="102a8-414">REMARKS</span></span>|<span data-ttu-id="102a8-415">String</span><span class="sxs-lookup"><span data-stu-id="102a8-415">String</span></span>|  
|<span data-ttu-id="102a8-416">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="102a8-416">OVERLOAD</span></span>|<span data-ttu-id="102a8-417">Int32</span><span class="sxs-lookup"><span data-stu-id="102a8-417">Int32</span></span>|  
|<span data-ttu-id="102a8-418">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="102a8-418">ORDINAL_POSITION</span></span>|<span data-ttu-id="102a8-419">Int32</span><span class="sxs-lookup"><span data-stu-id="102a8-419">Int32</span></span>|  
  
## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="102a8-420">Driver ODBC per Microsoft Jet</span><span class="sxs-lookup"><span data-stu-id="102a8-420">Microsoft Jet ODBC Driver</span></span>  
 <span data-ttu-id="102a8-421">Oltre alle raccolte di schemi comuni, il driver ODBC per Microsoft Jet supporta le raccolte di schemi specifici seguenti:</span><span class="sxs-lookup"><span data-stu-id="102a8-421">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="102a8-422">Tabelle</span><span class="sxs-lookup"><span data-stu-id="102a8-422">Tables</span></span>  
  
-   <span data-ttu-id="102a8-423">Indexes</span><span class="sxs-lookup"><span data-stu-id="102a8-423">Indexes</span></span>  
  
-   <span data-ttu-id="102a8-424">Colonne</span><span class="sxs-lookup"><span data-stu-id="102a8-424">Columns</span></span>  
  
-   <span data-ttu-id="102a8-425">Procedure</span><span class="sxs-lookup"><span data-stu-id="102a8-425">Procedures</span></span>  
  
-   <span data-ttu-id="102a8-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="102a8-426">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="102a8-427">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="102a8-427">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="102a8-428">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="102a8-428">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="102a8-429">Tables e Views</span><span class="sxs-lookup"><span data-stu-id="102a8-429">Tables and Views</span></span>  
  
|<span data-ttu-id="102a8-430">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="102a8-430">ColumnName</span></span>|<span data-ttu-id="102a8-431">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="102a8-431">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="102a8-432">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="102a8-432">TABLE_QUALIFIER</span></span>|<span data-ttu-id="102a8-433">String</span><span class="sxs-lookup"><span data-stu-id="102a8-433">String</span></span>|  
|<span data-ttu-id="102a8-434">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="102a8-434">TABLE_OWNER</span></span>|<span data-ttu-id="102a8-435">String</span><span class="sxs-lookup"><span data-stu-id="102a8-435">String</span></span>|  
|<span data-ttu-id="102a8-436">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="102a8-436">TABLE_NAME</span></span>|<span data-ttu-id="102a8-437">String</span><span class="sxs-lookup"><span data-stu-id="102a8-437">String</span></span>|  
|<span data-ttu-id="102a8-438">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="102a8-438">TABLE_TYPE</span></span>|<span data-ttu-id="102a8-439">String</span><span class="sxs-lookup"><span data-stu-id="102a8-439">String</span></span>|  
|<span data-ttu-id="102a8-440">REMARKS</span><span class="sxs-lookup"><span data-stu-id="102a8-440">REMARKS</span></span>|<span data-ttu-id="102a8-441">String</span><span class="sxs-lookup"><span data-stu-id="102a8-441">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="102a8-442">Colonne</span><span class="sxs-lookup"><span data-stu-id="102a8-442">Columns</span></span>  
  
|<span data-ttu-id="102a8-443">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="102a8-443">ColumnName</span></span>|<span data-ttu-id="102a8-444">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="102a8-444">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="102a8-445">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="102a8-445">TABLE_QUALIFIER</span></span>|<span data-ttu-id="102a8-446">String</span><span class="sxs-lookup"><span data-stu-id="102a8-446">String</span></span>|  
|<span data-ttu-id="102a8-447">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="102a8-447">TABLE_OWNER</span></span>|<span data-ttu-id="102a8-448">String</span><span class="sxs-lookup"><span data-stu-id="102a8-448">String</span></span>|  
|<span data-ttu-id="102a8-449">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="102a8-449">TABLE_NAME</span></span>|<span data-ttu-id="102a8-450">String</span><span class="sxs-lookup"><span data-stu-id="102a8-450">String</span></span>|  
|<span data-ttu-id="102a8-451">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="102a8-451">COLUMN_NAME</span></span>|<span data-ttu-id="102a8-452">String</span><span class="sxs-lookup"><span data-stu-id="102a8-452">String</span></span>|  
|<span data-ttu-id="102a8-453">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="102a8-453">DATA_TYPE</span></span>|<span data-ttu-id="102a8-454">Int16</span><span class="sxs-lookup"><span data-stu-id="102a8-454">Int16</span></span>|  
|<span data-ttu-id="102a8-455">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="102a8-455">TYPE_NAME</span></span>|<span data-ttu-id="102a8-456">String</span><span class="sxs-lookup"><span data-stu-id="102a8-456">String</span></span>|  
|<span data-ttu-id="102a8-457">PRECISION</span><span class="sxs-lookup"><span data-stu-id="102a8-457">PRECISION</span></span>|<span data-ttu-id="102a8-458">Int32</span><span class="sxs-lookup"><span data-stu-id="102a8-458">Int32</span></span>|  
|<span data-ttu-id="102a8-459">LENGTH</span><span class="sxs-lookup"><span data-stu-id="102a8-459">LENGTH</span></span>|<span data-ttu-id="102a8-460">Int32</span><span class="sxs-lookup"><span data-stu-id="102a8-460">Int32</span></span>|  
|<span data-ttu-id="102a8-461">SCALE</span><span class="sxs-lookup"><span data-stu-id="102a8-461">SCALE</span></span>|<span data-ttu-id="102a8-462">Int16</span><span class="sxs-lookup"><span data-stu-id="102a8-462">Int16</span></span>|  
|<span data-ttu-id="102a8-463">RADIX</span><span class="sxs-lookup"><span data-stu-id="102a8-463">RADIX</span></span>|<span data-ttu-id="102a8-464">Int16</span><span class="sxs-lookup"><span data-stu-id="102a8-464">Int16</span></span>|  
|<span data-ttu-id="102a8-465">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="102a8-465">NULLABLE</span></span>|<span data-ttu-id="102a8-466">Int16</span><span class="sxs-lookup"><span data-stu-id="102a8-466">Int16</span></span>|  
|<span data-ttu-id="102a8-467">REMARKS</span><span class="sxs-lookup"><span data-stu-id="102a8-467">REMARKS</span></span>|<span data-ttu-id="102a8-468">String</span><span class="sxs-lookup"><span data-stu-id="102a8-468">String</span></span>|  
|<span data-ttu-id="102a8-469">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="102a8-469">ORDINAL_POSITION</span></span>|<span data-ttu-id="102a8-470">Int32</span><span class="sxs-lookup"><span data-stu-id="102a8-470">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="102a8-471">Procedure</span><span class="sxs-lookup"><span data-stu-id="102a8-471">Procedures</span></span>  
  
|<span data-ttu-id="102a8-472">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="102a8-472">ColumnName</span></span>|<span data-ttu-id="102a8-473">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="102a8-473">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="102a8-474">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="102a8-474">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="102a8-475">String</span><span class="sxs-lookup"><span data-stu-id="102a8-475">String</span></span>|  
|<span data-ttu-id="102a8-476">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="102a8-476">PROCEDURE_OWNER</span></span>|<span data-ttu-id="102a8-477">String</span><span class="sxs-lookup"><span data-stu-id="102a8-477">String</span></span>|  
|<span data-ttu-id="102a8-478">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="102a8-478">PROCEDURE_NAME</span></span>|<span data-ttu-id="102a8-479">String</span><span class="sxs-lookup"><span data-stu-id="102a8-479">String</span></span>|  
|<span data-ttu-id="102a8-480">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="102a8-480">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="102a8-481">Int16</span><span class="sxs-lookup"><span data-stu-id="102a8-481">Int16</span></span>|  
|<span data-ttu-id="102a8-482">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="102a8-482">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="102a8-483">Int16</span><span class="sxs-lookup"><span data-stu-id="102a8-483">Int16</span></span>|  
|<span data-ttu-id="102a8-484">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="102a8-484">NUM_RESULT_SETS</span></span>|<span data-ttu-id="102a8-485">Int16</span><span class="sxs-lookup"><span data-stu-id="102a8-485">Int16</span></span>|  
|<span data-ttu-id="102a8-486">REMARKS</span><span class="sxs-lookup"><span data-stu-id="102a8-486">REMARKS</span></span>|<span data-ttu-id="102a8-487">String</span><span class="sxs-lookup"><span data-stu-id="102a8-487">String</span></span>|  
|<span data-ttu-id="102a8-488">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="102a8-488">PROCEDURE_TYPE</span></span>|<span data-ttu-id="102a8-489">Int16</span><span class="sxs-lookup"><span data-stu-id="102a8-489">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="102a8-490">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="102a8-490">ProcedureColumns</span></span>  
  
|<span data-ttu-id="102a8-491">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="102a8-491">ColumnName</span></span>|<span data-ttu-id="102a8-492">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="102a8-492">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="102a8-493">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="102a8-493">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="102a8-494">String</span><span class="sxs-lookup"><span data-stu-id="102a8-494">String</span></span>|  
|<span data-ttu-id="102a8-495">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="102a8-495">PROCEDURE_OWNER</span></span>|<span data-ttu-id="102a8-496">String</span><span class="sxs-lookup"><span data-stu-id="102a8-496">String</span></span>|  
|<span data-ttu-id="102a8-497">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="102a8-497">PROCEDURE_NAME</span></span>|<span data-ttu-id="102a8-498">String</span><span class="sxs-lookup"><span data-stu-id="102a8-498">String</span></span>|  
|<span data-ttu-id="102a8-499">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="102a8-499">COLUMN_NAME</span></span>|<span data-ttu-id="102a8-500">String</span><span class="sxs-lookup"><span data-stu-id="102a8-500">String</span></span>|  
|<span data-ttu-id="102a8-501">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="102a8-501">COLUMN_TYPE</span></span>|<span data-ttu-id="102a8-502">Int16</span><span class="sxs-lookup"><span data-stu-id="102a8-502">Int16</span></span>|  
|<span data-ttu-id="102a8-503">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="102a8-503">DATA_TYPE</span></span>|<span data-ttu-id="102a8-504">Int16</span><span class="sxs-lookup"><span data-stu-id="102a8-504">Int16</span></span>|  
|<span data-ttu-id="102a8-505">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="102a8-505">TYPE_NAME</span></span>|<span data-ttu-id="102a8-506">String</span><span class="sxs-lookup"><span data-stu-id="102a8-506">String</span></span>|  
|<span data-ttu-id="102a8-507">PRECISION</span><span class="sxs-lookup"><span data-stu-id="102a8-507">PRECISION</span></span>|<span data-ttu-id="102a8-508">Int32</span><span class="sxs-lookup"><span data-stu-id="102a8-508">Int32</span></span>|  
|<span data-ttu-id="102a8-509">LENGTH</span><span class="sxs-lookup"><span data-stu-id="102a8-509">LENGTH</span></span>|<span data-ttu-id="102a8-510">Int32</span><span class="sxs-lookup"><span data-stu-id="102a8-510">Int32</span></span>|  
|<span data-ttu-id="102a8-511">SCALE</span><span class="sxs-lookup"><span data-stu-id="102a8-511">SCALE</span></span>|<span data-ttu-id="102a8-512">Int16</span><span class="sxs-lookup"><span data-stu-id="102a8-512">Int16</span></span>|  
|<span data-ttu-id="102a8-513">RADIX</span><span class="sxs-lookup"><span data-stu-id="102a8-513">RADIX</span></span>|<span data-ttu-id="102a8-514">Int16</span><span class="sxs-lookup"><span data-stu-id="102a8-514">Int16</span></span>|  
|<span data-ttu-id="102a8-515">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="102a8-515">NULLABLE</span></span>|<span data-ttu-id="102a8-516">Int16</span><span class="sxs-lookup"><span data-stu-id="102a8-516">Int16</span></span>|  
|<span data-ttu-id="102a8-517">REMARKS</span><span class="sxs-lookup"><span data-stu-id="102a8-517">REMARKS</span></span>|<span data-ttu-id="102a8-518">String</span><span class="sxs-lookup"><span data-stu-id="102a8-518">String</span></span>|  
|<span data-ttu-id="102a8-519">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="102a8-519">OVERLOAD</span></span>|<span data-ttu-id="102a8-520">Int32</span><span class="sxs-lookup"><span data-stu-id="102a8-520">Int32</span></span>|  
|<span data-ttu-id="102a8-521">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="102a8-521">ORDINAL_POSITION</span></span>|<span data-ttu-id="102a8-522">Int32</span><span class="sxs-lookup"><span data-stu-id="102a8-522">Int32</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="102a8-523">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="102a8-523">ProcedureParameters</span></span>  
  
|<span data-ttu-id="102a8-524">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="102a8-524">ColumnName</span></span>|<span data-ttu-id="102a8-525">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="102a8-525">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="102a8-526">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="102a8-526">PROCEDURE_CAT</span></span>|<span data-ttu-id="102a8-527">String</span><span class="sxs-lookup"><span data-stu-id="102a8-527">String</span></span>|  
|<span data-ttu-id="102a8-528">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="102a8-528">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="102a8-529">String</span><span class="sxs-lookup"><span data-stu-id="102a8-529">String</span></span>|  
|<span data-ttu-id="102a8-530">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="102a8-530">PROCEDURE_NAME</span></span>|<span data-ttu-id="102a8-531">String</span><span class="sxs-lookup"><span data-stu-id="102a8-531">String</span></span>|  
|<span data-ttu-id="102a8-532">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="102a8-532">COLUMN_NAME</span></span>|<span data-ttu-id="102a8-533">String</span><span class="sxs-lookup"><span data-stu-id="102a8-533">String</span></span>|  
|<span data-ttu-id="102a8-534">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="102a8-534">COLUMN_TYPE</span></span>|<span data-ttu-id="102a8-535">Int16</span><span class="sxs-lookup"><span data-stu-id="102a8-535">Int16</span></span>|  
|<span data-ttu-id="102a8-536">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="102a8-536">DATA_TYPE</span></span>|<span data-ttu-id="102a8-537">Int16</span><span class="sxs-lookup"><span data-stu-id="102a8-537">Int16</span></span>|  
|<span data-ttu-id="102a8-538">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="102a8-538">TYPE_NAME</span></span>|<span data-ttu-id="102a8-539">String</span><span class="sxs-lookup"><span data-stu-id="102a8-539">String</span></span>|  
|<span data-ttu-id="102a8-540">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="102a8-540">COLUMN_SIZE</span></span>|<span data-ttu-id="102a8-541">Int32</span><span class="sxs-lookup"><span data-stu-id="102a8-541">Int32</span></span>|  
|<span data-ttu-id="102a8-542">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="102a8-542">BUFFER_LENGTH</span></span>|<span data-ttu-id="102a8-543">Int32</span><span class="sxs-lookup"><span data-stu-id="102a8-543">Int32</span></span>|  
|<span data-ttu-id="102a8-544">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="102a8-544">DECIMAL_DIGITS</span></span>|<span data-ttu-id="102a8-545">Int16</span><span class="sxs-lookup"><span data-stu-id="102a8-545">Int16</span></span>|  
|<span data-ttu-id="102a8-546">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="102a8-546">NUM_PREC_RADIX</span></span>|<span data-ttu-id="102a8-547">Int16</span><span class="sxs-lookup"><span data-stu-id="102a8-547">Int16</span></span>|  
|<span data-ttu-id="102a8-548">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="102a8-548">NULLABLE</span></span>|<span data-ttu-id="102a8-549">Int16</span><span class="sxs-lookup"><span data-stu-id="102a8-549">Int16</span></span>|  
|<span data-ttu-id="102a8-550">REMARKS</span><span class="sxs-lookup"><span data-stu-id="102a8-550">REMARKS</span></span>|<span data-ttu-id="102a8-551">String</span><span class="sxs-lookup"><span data-stu-id="102a8-551">String</span></span>|  
|<span data-ttu-id="102a8-552">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="102a8-552">COLUMN_DEF</span></span>|<span data-ttu-id="102a8-553">String</span><span class="sxs-lookup"><span data-stu-id="102a8-553">String</span></span>|  
|<span data-ttu-id="102a8-554">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="102a8-554">SQL_DATA_TYPE</span></span>|<span data-ttu-id="102a8-555">Int16</span><span class="sxs-lookup"><span data-stu-id="102a8-555">Int16</span></span>|  
|<span data-ttu-id="102a8-556">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="102a8-556">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="102a8-557">Int16</span><span class="sxs-lookup"><span data-stu-id="102a8-557">Int16</span></span>|  
|<span data-ttu-id="102a8-558">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="102a8-558">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="102a8-559">Int32</span><span class="sxs-lookup"><span data-stu-id="102a8-559">Int32</span></span>|  
|<span data-ttu-id="102a8-560">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="102a8-560">ORDINAL_POSITION</span></span>|<span data-ttu-id="102a8-561">Int32</span><span class="sxs-lookup"><span data-stu-id="102a8-561">Int32</span></span>|  
|<span data-ttu-id="102a8-562">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="102a8-562">IS_NULLABLE</span></span>|<span data-ttu-id="102a8-563">Stringa</span><span class="sxs-lookup"><span data-stu-id="102a8-563">String</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="102a8-564">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="102a8-564">See Also</span></span>  
 [<span data-ttu-id="102a8-565">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="102a8-565">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
