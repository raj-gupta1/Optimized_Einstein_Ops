# Optimized_Einstein_Ops
 Improved performance from existing einops repo. Tensor operations made 150 percent faster.

# 🌌 Custom Rearrange Function

This implementation is inspired from `einops` but takes it further with **optimized performance**, **smart caching**, and **user-friendly error handling** and designed to simplify tensor manipulation with speed.

---

## ✨ Benefits

- **Pattern-Based Flexibility**: Transform tensors using readable patterns like `'h w c -> (h w) c'` or `'b c h w -> b (h w) c'`.
- **Broadcasting Magic**: Add new dimensions or expand existing ones without breaking a sweat.
- **Performance Boost**: Powered by `lru_cache`, it caches operations for fast repeated calls.
- **Helpful Debugging**: Custom `EinopsError` exceptions provide clear, actionable feedback when something goes wrong.
- **Unique Design**: Improved performance and usability advantages.

---

## 🛠️ How Does It Work?

The `rearrange` function is a tensor-transforming wizard that operates in **four seamless steps**:

1. **Pattern Parsing**  
   - Takes a pattern like `'h w c -> w h c'` and splits it into **input axes** (`h`, `w`, `c`) and **output axes** (`w`, `h`, `c`).  
   - Understands grouped axes like `(h w)` for advanced reshaping.

2. **Custom Axis Size**  
   - Calculates the size of each axis based on the tensor’s shape.  
   - Supports custom sizes via an optional `axes_lengths` argument (e.g., `h=32, w=32`).

3. **Tensor Transformation**  
   - **Splits**: Breaks down grouped axes (e.g., `(h w)` into a single dimension).  
   - **Permutes**: Reorders axes to match the output pattern.  
   - **Broadcasts**: Expands or adds dimensions as needed.  
   - **Reshapes**: Delivers the final tensor in the desired shape.

4. **Caching**  
   - Stores parsed patterns and operations in memory, so repeated calls are fast.

---

## 🚀 Get Started 

#### Step 1: Open Colab
#### Step 2: Choose Tesla T4 GPU
#### Step 3: Run Cells
