# Plan Command

This command creates detailed solution plans in markdown format for technical problems that users are experiencing.

## Usage

### Basic Usage
```
/plan [problem description and error messages]
```

### Custom Path Usage
```
/plan:{relative_path_for_document} [problem description and error messages]
```

## Command Implementation

### Path Parsing and Processing
1. **Command Parsing**
   - `/plan` format: Uses default `docs/` directory
   - `/plan:{path}` format: Uses user-specified path
   - Automatically creates path if it doesn't exist

2. **Filename Generation**
   - Extracts problem keywords to generate filename
   - Format: `{problem-keywords}-plan.md`
   - Timestamp option to prevent duplicates

### Problem Analysis and Plan Development
1. **Problem Situation Analysis**
   - Error message interpretation
   - Root cause identification
   - Impact scope analysis

2. **Solution Plan Development**
   - Step-by-step solution approaches
   - Priority-based methodology
   - Include code examples

3. **Document Generation**
   - Create markdown file in specified path
   - Write structured plan document

4. **Execution Guide**
   - Specific execution steps
   - Verification and testing methods
   - Precautions and risk factors

## Examples

### Basic Path Usage Example
```
/plan ECR Repository is being repeatedly deleted. Error message: CannotPullContainerError: pull image manifest has been retried 1 time(s): failed to resolve ref
```
→ Document location: `docs/ecr-repository-deletion-plan.md`

### Custom Path Usage Examples
```
/plan:new_common_auth/iac/docs ECR Repository is being repeatedly deleted. Error message: CannotPullContainerError: pull image manifest has been retried 1 time(s): failed to resolve ref
```
→ Document location: `new_common_auth/iac/docs/ecr-repository-deletion-plan.md`

```
/plan:troubleshooting/docker Invalid containerPort error occurs during Docker image build
```
→ Document location: `troubleshooting/docker/containerport-error-plan.md`

### Processing Flow
For the above input, the following operations are performed:
1. **Path Parsing**: Verify and create `new_common_auth/iac/docs` path
2. **Problem Analysis**: Image reference failure due to ECR Repository deletion
3. **Plan Development**: Repository protection settings, Data Source references, etc.
4. **Document Generation**: Create `ecr-repository-deletion-plan.md` in specified path
5. **Execution Guide**: Pulumi import, configuration changes, etc.

## Document Structure

Generated plan documents follow this structure:

```markdown
# [Problem Name] Solution Plan

## 🎯 Objectives
- Primary objective 1
- Primary objective 2

## 🔍 Problem Analysis
### Current Situation
### Root Cause

## 📋 Solution Plan
### 1. Step-by-Step Solutions
### 2. Code Examples
### 3. Implementation Order

## ⚠️ Precautions
### Risk Factors
### Verification Items

## 💡 Execution Guide
### Immediate Actions
### Short-term Improvements
### Long-term Plans
```

## Path Management Rules

1. **Relative Path Usage**: Use relative paths based on project root
2. **Automatic Directory Creation**: Automatically create path if it doesn't exist
3. **Filename Duplication Handling**: Add timestamp if same filename exists
4. **Path Validation**: Output error messages for invalid paths or permission issues

## Advanced Features

- **Template Selection**: Provide various templates based on problem type
- **Tag System**: Automatically add tags by problem category
- **Link Connection**: Cross-reference with related documents or issues
- **Progress Tracking**: Provide step-by-step checklists for resolution

This command enables you to quickly create systematic and actionable problem-solving plans at any desired location.