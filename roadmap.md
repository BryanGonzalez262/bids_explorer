# BIDS Explorer Development Roadmap

## 1. Setter for BidsArchitecture attributes (High Priority)
- Add setter for dataset criteria attributes to allow dynamic updating.

## 2. Add factory for BidsArchitecture (High Priority)
- Add factory for BidsArchitecture to allow for dynamic creation of objects
instead of copy instances.

## 3. Regex implementation for more complex queries (High Priority)
- Implement regex support for more flexible query patterns.

## 4. Strict Selection Implementation (High Priority)
### 4.1 Complete Dataset Selection
- Implement method to select subjects based on complete dataset criteria
- Add functionality to verify if subjects have all required sessions
- Add functionality to verify if subjects have all required datatypes
- Example usage:
```python
# Select only subjects that have both sessions "01" and "02"
complete_data = bids.strict_select(sessions=["01", "02"])
# Select subjects with all specified datatypes
complete_data = bids.strict_select(datatypes=["eeg", "meg", "anat"])
```
### 4.2 Selection Reporting
- Create reporting mechanism for strict selection results
- Include detailed information about why subjects were excluded
- Example usage:

```python
# Get report of why subjects were excluded
complete_data, report = bids.strict_select(
    sessions=["01", "02"],
    return_report=True
)
print(report)  # Shows which subjects were missing which sessions
```

## 5. Enhanced Validation Features (Medium Priority)
### 5.1 BIDS Specification Compliance
- Add more comprehensive BIDS validation checks
- Implement validation against specific BIDS versions
- Add support for custom validation rules

### 5.2 Data Quality Checks
- Add file integrity verification
- Implement metadata consistency checks
- Add support for custom quality metrics

## 6. Query Enhancement (Medium Priority)
### 6.1 Advanced Query Features
- Add support for regular expressions in queries
- Implement complex logical operations (AND, OR, NOT) in queries
- Add support for nested queries

### 6.2 Query Performance Optimization
- Implement query caching
- Add index-based searching
- Optimize memory usage for large datasets

## 7. Data Management Features (Low Priority)
### 7.1 Dataset Modification
- Add support for safe dataset modifications
- Implement version control for dataset changes
- Add support for dataset reorganization

### 7.2 Export and Import
- Add support for exporting subsets of data
- Implement import validation
- Add support for different export formats

## 8. Documentation and Examples (Ongoing)
### 8.1 API Documentation
- Enhance docstring coverage
- Add more usage examples
- Create tutorials for common use cases

### 8.2 User Guides
- Create comprehensive user guide
- Add best practices documentation
- Include troubleshooting guide

## 9. Testing and Quality Assurance (Ongoing)
### 9.1 Test Coverage
- Increase test coverage
- Add integration tests
- Implement performance benchmarks

### 9.2 Quality Metrics
- Add code quality metrics
- Implement automated style checking
- Add security scanning

## Implementation Notes

### Key Files to Modify
1. Core Architecture (`src/bids_explorer/architecture/architecture.py`):
```python:src/bids_explorer/architecture/architecture.py
startLine: 23
endLine: 144
```

2. Validation Module (`src/bids_explorer/architecture/validation.py`):
```python:src/bids_explorer/architecture/validation.py
startLine: 28
endLine: 176
```

### Testing Strategy
- Unit tests for each new feature
- Integration tests for complex operations
- Performance tests for large datasets

### Documentation Requirements
- API documentation for new methods
- Usage examples in README
- Detailed implementation notes
- Make a cookbook of examples with jupyter notebooks.
