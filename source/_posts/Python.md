---
title: Python
---

## Basics

convert '1' to '001' str

```py
f'{i:03}'
```

### Lambda function
```python
max_vb = lambda x,y: (x/y-1)/(x/y+1);
```

## Plot

### Plot in function

```python
## define function to manipulate fig and ax
def plotfunc()
    dis = np.array(pdis)
    fig, (ax1, ax2,ax3) = plt.subplots(1, 3,figsize=(18,6))
    u0 = ax1.imshow(dis[0],cmap=cmap,vmin=0, vmax=vmax0)
    #ax1.axis('off')
    ax1.set_xticks([])
    ax1.tick_params(labelsize=15) 
    #ax1.set_yticks([])
    ax1.set_title())
    clb = plt.colorbar()
    clb.ax.tick_params(labelsize=15) 
    u1 = ax2.imshow()
    ax2.set_title()
    ax2.axis('off')
    clb = plt.colorbar(u1,ax=ax2, fraction=0.046, pad=0.04,orientation="horizontal")
    clb.ax.tick_params(labelsize=15) 
    utot = ax3.imshow(utot,cmap=cmap,vmin=0, vmax=vmax3)
    ax3.axis('off')
    ax3.set_title()
    clb = plt.colorbar(utot,ax=ax3,fraction=0.046, pad=0.04,orientation="horizontal")
    clb.ax.tick_params(labelsize=15) 
    return fig
```

### Basic figure

### Subplots

### Histogram

### Styles: dashed line style cycle


## Math
